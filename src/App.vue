<template>
  <nav class="navbar navbar-expand-md navbar-dark bg-dark mb-4">
        <div class="container-fluid">
            <router-link class="navbar-brand" to="/">Home</router-link>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarCollapse" aria-controls="navbarCollapse" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
            </button>
            <div>
            <ul class="navbar-nav me-auto mb-2 mb-md-0">
                <li class="nav-item">
                <router-link class="nav-link" to="/login">Login</router-link>
                </li>
                <li class="nav-item">
                <router-link class="nav-link" to="/register">Register</router-link>
                </li>
            </ul>
            </div>
        </div>
    </nav>

  <main class="form-signin">

  <router-view/>
  
  </main>
  
</template>

<script>

// import NavBar from "@/components/NavBar.vue";

export default {
  
}
</script>

<style>


.form-signin {
  text-align: center;
  max-width: 330px;
  padding: 15px;
}

.form-signin .form-floating:focus-within {
  z-index: 2;
}

.form-signin input[type="email"] {
  margin-bottom: -1px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}

.form-signin input[type="password"] {
  margin-bottom: 10px;
  border-top-left-radius: 0;
  border-top-right-radius: 0;
}
</style>

