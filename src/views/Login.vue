<template>
  <form @submit.prevent="submit">

    <h1 class="h3 mb-3 fw-normal">Please sign in</h1>

    <input v-model="data.email" type="email" class="form-control" placeholder="name@example.com">
    <input v-model="data.password" type="password" class="form-control" placeholder="Password">

    <button class="w-100 btn btn-lg btn-primary" type="submit">Sign in</button>
  </form>
</template>

<script>
import { reactive } from "vue"
import { useRouter } from "vue-router"

export default {
  name: `Login`,
  
  setup() {
    const data = reactive({
      email: '',
      password: '',
    });

    const router = useRouter();

    const submit = async () => {
      await fetch("http://localhost:8000/api/login", {
        method: "POST",
        headers: {"content-type": "application/json"},
        credentials: "include",
        body: JSON.stringify(data)
      });
      
      await router.push("/")
    }


    return {
      data,
      submit
    }
  }
}
</script>