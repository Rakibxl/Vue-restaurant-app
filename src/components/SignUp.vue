<template>
<img class="logo" alt="Restaurant logo" src="../assets/chilis.png"/>
<h1> Sign up</h1>  

<div class="register">
    <input type="text" v-model="name" placeholder="Enter name" />
    <input type="text" v-model="email"  placeholder="Enter email" />
    <input type="text" v-model="password" placeholder="Enter password" />
    <button v-on:click="signUp">Sign Up</button>
</div>

</template>

<script>
import axios from 'axios'

export default {
    name: 'SignUp',
    data()
    {
        return {
            name: '',
            email: '',
            password: '',
        }
    },
    methods:{
        async signUp()
        {
            // console.warn('sign up', this.name, this.email, this.password);
            let result = axios.post("http://localhost:3000/user",
            {
                email: this.email,
                password : this.password,
                name:this.name
            }
            
            );

            console.warn(result);
            if ((await result).status == 201)
            {
                alert("sign up done");
                localStorage.setItem("user-info", JSON.stringify(result.data));
            }
        }
    }
}
</script>

<style scoped>
.logo {
    width: 100px;
}


.register input {
    width: 300px;
    height: 40px;
    padding-left: 20px;
    display: block;
    margin-bottom: 30px;
    margin-left: auto;
    margin-right: auto;
    border: 1px solid green;
}

.register button{
    width:320px;
    height: 40px;
    border: 1px solid green;
    background: green;
    color: #fff;
    cursor: pointer;
}


</style>