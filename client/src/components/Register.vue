<template>
    <div class="reg-wrapper">
        <h1>Register</h1>
        <input
                type="email"
                name="email"
                v-model="email"
                :placeholder="placeholderValue"
        />
        <br>
        <input
                type="password"
                name="password"
                v-model="password"
                placeholder="password"
        />
        <br>
        <button
                @click="register"
        >
            Register
        </button>
    </div>
</template>

<script>
    import AuthService from '../services/AuthService'

    let Register = {
        name: 'Register',
        data() {
            return {
                email: '',
                password: '',
                placeholderValue: 'email'
            }
        },
        methods: {
            async register() {
                await AuthService.register({
                    email: this.email,
                    password: this.password
                });
            }
        },
        mounted() {
            setTimeout(() => {
                this.placeholderValue = 'You need to login Dude!';
            }, 2000)
        }
    };

    export default Register
</script>

<style lang="scss" scoped>

</style>
