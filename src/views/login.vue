<template>
<div class="home">
  <h3 id="login">Login</h3>
  <input class="ip" type="email" placeholder="Email" v-model="loginemail">
  <br>
  <input class="ip" type="password" placeholder="Password" v-model="loginpsw">
    <br>
  <button class="ip" v-on:click="login">Login</button>

  </div>
  <div>
      <h2>{{wlc}} {{name}}</h2>
    <!-- <p class="text"></p> -->
    <p class="text">{{email}}</p>
    <p class="text">{{PhoneNo}}</p>
    <h4 class="text">{{usernotfound}}</h4>
  </div>
</template>

<script>
export default {
    name:'login',
    data(){
        return{
            name:"",
            email:"",
            psw:"",
            PhoneNo:"",
            loginname:"",
            loginpsw:"",
            usernotfound:"",
            wlc:""

            

        }
    },
    // props:['name','email','psw','PhoneNo'],
    methods:{
        login(){
             console.log(localStorage.getItem("name")); 
             console.log(localStorage.getItem("email")); 
             console.log(localStorage.getItem("psw")); 
             console.log(localStorage.getItem("PhoneNo"));
             
             
             
             if(localStorage.getItem("email")==this.loginemail && localStorage.getItem("psw")==this.loginpsw){
                 this.email = localStorage.getItem("email");
             this.psw = localStorage.getItem("psw");
                 this.name = localStorage.getItem("name");
                 this.PhoneNo = localStorage.getItem("PhoneNo");
                 this.wlc="welcome"

             }
             else{
                 this.usernotfound="Entered wrong Details"
             }
        }
    }

    

}
</script>

<style>
.home{
  background-color: darkslategray;
  vertical-align: middle;
   display: inline-flexbox;
   width: 40%;
   margin-left: 30%;
   border-radius: 50px;
   margin-top: 20px;
   padding-top:20px ;
   padding-bottom: 30px;
  
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
.text{
    color: green;
    font: 30px ;
}
</style>