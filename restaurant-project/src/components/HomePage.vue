<template>
    <HeaderSec></HeaderSec>
    <h1>Hello User, Welcome on Home Page</h1>
</template>
<script>
import HeaderSec from './HeaderSec.vue';
export default {
    name: 'HomePage',
    components: {
        HeaderSec
    },
    mounted() {
        let user = localStorage.getItem('user-info');
        if (!user) {
            this.$router.push({ name: "SignUp" });
        }
    }
}
</script>
