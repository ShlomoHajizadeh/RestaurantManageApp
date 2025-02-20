<template>
    <img class="logo" src="../assets/logo.png" />
    <h1>Sign Up</h1>
    <div class="register">
        <input type="text" v-model="name" placeholder="Enter Name" />
        <input type="email" v-model="email" placeholder="Enter Email" />
        <input type="password" v-model="password" placeholder="Enter Password" />
        <button v-on:click="signUp">Sign Up</button>
    </div>
</template>
<script>
import axios from 'axios';
export default {
    name: 'SignUp',
    data()
    {
        return {
            name: "Shlomo",
            email: "suleyman.hacizade1@gmail.com",
            password: "1234567654533455676453",
        }
    },
    methods: {
       async signUp() 
        {
            let result = await axios.post("http://localhost:3000/users", {
                email: this.email,
                password: this.password,
                name: this.name
            });

            console.log(result);
            if(result.status == 201)
            {
                alert("User created successfully");
                localStorage.setItem("user-info", JSON.stringify(result.data));
            }
        }
    }
}

</script>

<style>
.logo {
    width: 100px;
}
.register input {
    width: 300px;
    height: 40px;
    padding-left: 20px;
    display: block;
    margin-bottom: 30px;
    margin-right: auto;
    margin-left: auto;
    border: 1px solid skyblue;
}

.register button {
    width: 320px;
    height: 40px;
    border: 1px solid skyblue;
    background-color: skyblue;
    color: #fff;
    cursor: pointer;
}
</style>