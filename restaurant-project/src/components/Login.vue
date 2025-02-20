<template>
    <img class="logo" src="../assets/logo.png" />
    <h1>Login</h1>
    <div class="login">
        <input type="email" v-model="email" placeholder="Enter Email" />
        <input type="password" v-model="password" placeholder="Enter Password" />
        <button v-on:click="signUp">Login</button>
        <p>
            <router-link to="/sign-up">Sign Up</router-link>
        </p>
    </div>
</template>


<script>
export default {
    name: 'UserLogin'
}
</script>