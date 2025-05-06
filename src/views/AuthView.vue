<template>
<div class="container-xxl mt-5 p-4 border rounded-5 bg-light shadow-sm" style="max-width: 375px;">

<form>
  <div class="mb-3">
    <label for="exampleInputEmail1" class="form-label" >E-m@il</label>
    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" v-model="email">
</div>

  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword1" v-model="password">
  </div>

  <button type="submit" class="btn custom-btn mt-2 w-100" @click="authUser">Submit</button>

</form>

</div>
</template>

<script lang="ts" setup>
import {Ref,ref} from "vue"
import AuthService from "../services/AuthService";

// service : https://hfp69ilv.directus.app/auth/login
// email   : testuser@gogodev.net
// password: 12345678

let email:Ref<string> = ref('');
let password:Ref<string> = ref('');

const authUser = async () => {
  
  const auth = new AuthService();
  const response = await auth.login(email.value, password.value);

  if (response){
    alert('Login success!!')
  }else{
    alert('Login error!!')
  }


}







</script>

<style scoped>
 label {
    text-align: left;
    display: block;
    margin-bottom: 5px;
    font-weight: bold;
    color: #42b983;
    font-size: 16px;
 
  
  }

  .custom-btn {
  background-color: #42b983;
  color: white;
  border-color: #42b983;
}

.custom-btn:hover {
  background-color: darkslategray ;
  color: #fff;
  border-color: darkslategray;
}




</style>