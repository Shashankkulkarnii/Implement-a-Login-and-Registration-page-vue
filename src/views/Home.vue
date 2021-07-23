<template>
<div>
  <img alt="Vue logo" src="../assets/logo.png">
  <div class="home">
    
    <br>
    <h3 id="login">Registration Form</h3>
    <input class="ip" type="text" placeholder="Name" v-model="uname">
    <br>
  <input class="ip" type="email" placeholder="Email" v-model="email">
  <br>
  <input class="ip" type="password" placeholder="Password" v-model="psw">
  <br>
  <input class="ip" type="number" placeholder="Phone No" v-model="PhoneNo">
  <br>  
  <button class="ip" v-on:click="click">click </button>
  <br>
  <br>  
    <!-- <registration/> -->
    <router-link id="login" :to="{name :'login'}">
      Login
    </router-link>
      </div>
      </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
// import registration from '@/components/registration.vue'



export default {
  name: 'Home',
  components: {
    HelloWorld,
  
  },
  data(){
    return{
        uname:null,
        email:"",
        psw:"",
        PhoneNo:"",
    }
    
},
methods:{
    click(){
              if (typeof(Storage) !== "undefined") {
    localStorage.setItem("name",this.uname);
    localStorage.setItem("email",this.email);
    localStorage.setItem("psw",this.psw);
    localStorage.setItem("PhoneNo",this.PhoneNo);
    console.log(localStorage.getItem("name")); 
    console.log(localStorage.getItem("email")); 
    console.log(localStorage.getItem("psw")); 
    console.log(localStorage.getItem("PhoneNo")); 
    // document.getElementById("result").innerHTML= localStorage.getItem("name");
    // localStorage.removeItem("name");
    // document.getElementById("Delresult").innerHTML= localStorage.getItem("name");
    // console.log(localStorage.getItem("name")); 
}
else{
    console.log("browser not supported local storage");
}
        

    }

    }
}
</script>
<style >
.home{
  background-color: darkslategray;
  vertical-align: middle;
   display: inline-flexbox;
   width: 30%;
   margin-left: 30%;
   border-radius: 50px;
   margin-top: 20px;
   padding-top:20px ;
   padding-bottom: 30px;
   border: 2px solid green;
  
}
.ip{
  border: 2px solid green;
  border-radius: 10px;
  margin-top: 20px;
  background-color: aliceblue;
  display: inline-flexbox;
   vertical-align: middle;
}
#login{
  margin-top: 20px;
  color: green;
  text-decoration: none;
}
</style>
