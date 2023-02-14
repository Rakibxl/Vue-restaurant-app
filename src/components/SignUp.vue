<template>
<img class="logo" alt="Restaurant logo" src="../assets/chilis.png"/>
<h1> Sign up</h1>  

<div class="register">
    <input type="text" placeholder="Enter name" />
    <input type="text" placeholder="Enter email" />
    <input type="text" placeholder="Enter password" />
    <button>Sign Up</button>
</div>

</template>

<script>
export default {
    name: 'SignUp'
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