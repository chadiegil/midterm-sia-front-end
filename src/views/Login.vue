<template>
  <div class="container mt-5 w-25 border p-3">
    <label class="text-center">
      <h1>Login</h1>
    </label>
    <form @submit="login">
      <div class="form-group mt-3">
        <input
          type="email"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
          placeholder="Enter email"
          v-model="email"
        />
      </div>
      <div class="form-group mt-3">
        <input
          type="password"
          class="form-control"
          id="exampleInputPassword1"
          placeholder="Password"
          v-model="password"
        />
      </div>

      <button type="submit" class="btn btn-primary mt-4">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: "",
      user: "",
    };
  },
  methods: {
    async login(e) {
      e.preventDefault();

      const loginRequest = {
        email: this.email,
        password: this.password,
      };

      fetch("http://127.0.0.1:8000/api/login/", {
        method: "POST",
        headers: {
          Accept: "application/json",
          "Content-Type": "application/json",
        },
        body: JSON.stringify(loginRequest),
      })
        .then((response) => {
          if (response.status === 200) {
            this.$router.push({ path: "/" });
          }
        })
        .catch((err) => console.log(err));
    },
  },
  mounted() {
    this.login();
    console.log("mounted");
  },
};
</script>

<style></style>
