<template>
   <div>
       <label>Witaj {{ username}}</label>
       
       <a @click="logOut()">Wyloguj</a>
   </div>
</template>

<script>
export default {

 props:['username'],
 
 methods: {
     logOut() {
         this.$emit('logout');
     }
 }
}
</script>