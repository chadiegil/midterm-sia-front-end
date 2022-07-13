<template>
  <div class="container mt-5 w-25 border p-3">
    <label class="text-center">
      <h1>Register</h1>
    </label>
    <form @submit="register">
      <div class="form-group mt-3">
        <input
          type="text"
          class="form-control"
          id="text"
          placeholder="name"
          v-model="fname"
        />
      </div>
      <div class="form-group mt-3">
        <input
          type="text"
          class="form-control"
          id="text"
          placeholder=" lastname"
          v-model="lname"
        />
      </div>
      <div class="form-group mt-3">
        <input
          type="text"
          class="form-control"
          id="text"
          placeholder="mobile"
          v-model="mobile"
        />
      </div>
      <div class="form-group mt-3">
        <input
          type="password"
          class="form-control"
          id="text"
          placeholder="password"
          v-model="password"
        />
      </div>
      <div class="form-group mt-3">
        <input
          type="email"
          class="form-control"
          id="text"
          placeholder="email"
          v-model="email"
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
      lname: "",
      fname: "",
      mobile: "",
      user: "",
    };
  },
  methods: {
    async register(e) {
      e.preventDefault();

      const registerRequest = {
        email: this.email,
        password: this.password,
        lname: this.lname,
        fname: this.fname,
        mobile: this.mobile,
      };

      fetch("http://127.0.0.1:8000/api/register/", {
        method: "POST",
        headers: {
          Accept: "application/json",
          "Content-Type": "application/json",
        },
        body: JSON.stringify(registerRequest),
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
    this.register();
    console.log("mounted");
  },
};
</script>

<style></style>
