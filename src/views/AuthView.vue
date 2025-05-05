<template>
 <div class="container col-4 mt-2 border rounded-5 text-bg-ligth  p-5"  >
  
<form>
  <div class="mb-3">
    <label for="exampleInputEmail1" class="form-label" >Email address</label>
    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" v-model="email">
</div>
  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword1" v-model="password">
  </div>

  <button type="submit" class="btn btn-primary mt-2">Submit</button>

</form>
</div>
</template>

<script lang="ts" setup>
import {Ref,ref} from "vue"
let email:Ref<string> = ref('');
let password:Ref<string> = ref('');

</script>

<style scoped>
 label {
    text-align: left;
    display: block;
    margin-bottom: 5px;
    font-weight: bold;
    color: black;
    font-size: 16px;
 
  
  }
</style>