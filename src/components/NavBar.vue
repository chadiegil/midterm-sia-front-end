<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light custom">
    <div class="container hover-links">
      <router-link to="/" class="navbar-brand hover-links"
        >Blog App</router-link
      >
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <router-link to="/" class="nav-link hover-links">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/about" class="nav-link hover-links"
              >About</router-link
            >
          </li>
          <li class="nav-item">
            <router-link to="/contact" class="nav-link hover-links"
              >Contact</router-link
            >
          </li>
          <li class="nav-item">
            <router-link to="/login" class="nav-link hover-links"
              >Login</router-link
            >
          </li>
          <li class="nav-item">
            <router-link to="/register" class="nav-link hover-links"
              >Register</router-link
            >
          </li>
          <li class="nav-item">
            <router-link to="/logout" class="nav-link hover-links"
              >Logout</router-link
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style scoped>
.hover-links:hover {
  color: blue;
}

.right-nav {
  width: 30%;
  display: flex;
  align-items: center;
  justify-content: center;
  align-content: center;
}
.right-nav ul {
  margin: 0;
}

.right-nav li {
  list-style: none;
}
.c-link {
  color: black;
}

.c-link:hover {
  color: blue;
}
</style>
