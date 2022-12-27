<template>
    {{ message }}
</template>

<script lang="ts">

import { onMounted, ref } from 'vue';

export default {
    name: `Home`,
    setup() {

        const message = ref("You are not logged in");

        onMounted(async () => {
            const response = await fetch("http://localhost:8000/api/user", {
                method: "GET",
                headers: { "content-type": "application/json" },
                credentials: "include",
            });

            const content = await response.json();
            message.value = "Hi " + content.name;
        });

        return {
            message
        }
    }
}
</script>