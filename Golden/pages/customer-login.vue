<template>
  <div>
  <input type="text" name="username" v-model="input.username" placeholder="Username" />
  <input type="password" name="password" v-model="input.password" placeholder="Password" />
  <button type="button" v-on:click="login()">Login</button>
  </div>
</template>

<script>
    export default {
        name: 'Login',
        async asyncData() {
        const data = await fetch("http://localhost:5000/customers", {
        method: "GET"
        });
        return {
        customers: await data.json(),


                input: {
                    username: "",
                    password: ""
                }
            }
        },
        methods: {
            login() {
                if(this.input.username != "" && this.input.password != "") {
                    if(this.customers.map(a => a.email).includes(this.input.username) == true && this.customers.map(a => a.password).includes(this.input.password) == true) {
                        // this.$emit("authenticated", true);
                        // this.$router.replace({ name: "secure" });
                        alert("hej")
                    } else {
                        console.log("The username and / or password is incorrect");
                    }
                } else {
                    console.log("A username and password must be present");
                }
            }
        }
    }
</script>
<style>

</style>
