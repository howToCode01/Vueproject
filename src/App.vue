<script >
export default{
 
  data(){
    return{
      hello:true,
      signUp:false,
      signIn:false,
      changePassword:false,
      password:'',
      passwordCheck:'',
      inputStrength:false,
      inputCheck:false,
      passwordChange:''
    }
  },
  methods:{
    deleteHello(){
      setTimeout(()=>{this.hello=false},2000)
    },
    checkStrength(){
      this.inputStrength=true
    },
    checkInput(){
      this.inputCheck=true
    },
  SignUpbutton(){
    if(!this.signIn&&!this.hello&&!this.changePassword){
   this.signUp=true
  }},
  SignInButton(){
   if(!this.signUp&&!this.hello&&!this.changePassword){
    this.signIn=true
   }
  },
  openSignIn(){
    this.signUp=false;
    this.signIn=true
  },
  forgotPassword(){
  this.signIn=false;
this.changePassword=true
  },
  openSignUp(){
    this.signIn=false;
    this.signUp=true;
  }
},
  mounted(){
    this.deleteHello()}
    ,
    watch:{
      password(){
        this.checkStrength()
      },
      passwordChange(){
        this.checkInput()
      }
    }}
</script>


<template>
  <Transition >
  <div class="modal-hello" v-show="hello">
    <div class="modal-hello-item">
      <div class="modal-hello-text">HELLO!</div>
    </div>
  </div>
</Transition>
  <div>
  <div class="nav-bar">
    <div class="nav-bar-item">
    <div class="main_sign-in"> 
      <app-button @click="SignInButton"></app-button>
      <app-button class="main-button" @click="SignUpbutton">SIGN UP</app-button>
      </div>
    </div>
  </div>
</div>
<sign-up-in-form v-show="signUp">
<input-sign />
<input-sign placeholder="Full Name"/>

<password-checker :password="password" :input-strength="inputStrength">
  <div class="input-eye__block">
<input-sign class="input-check" type="password" id="password" v-model:passwordNew="password" placeholder="Password" />
<div class="input-check__icon">
  <img src="./images/eye-off.svg" alt="eyeoff" class="input-check__img">
</div>
</div>
</password-checker>

<div class="input-eye__block ">
<input-sign type="password" placeholder="Confirm Password"/>
<div class="input-check__icon input-check__icon2 ">
  <img src="./images/eye-off.svg" alt="eyeoff" class="input-check__img">
</div>
</div>
<app-button-sign ></app-button-sign>
<p class="sign-text">Have an account?<span @click="openSignIn"> Log in</span></p>
</sign-up-in-form>
<sign-up-in-form v-show="signIn">
  <input-sign></input-sign>
  <div class="input-eye__block">
  <input-sign type="password" placeholder="Password"></input-sign>
  <div class="input-check__icon input-check__icon2 ">
    <img src="./images/eye-off.svg" alt="eyeoff" class="input-check__img">
  </div>
  </div>
 <p class="sign-text sign_forgot"><span @click="forgotPassword">Forgot Password?</span></p>
  <app-button-sign >SIGN IN</app-button-sign>
  <p class="sign-text">Don't have an account? <span @click="openSignUp">Sign up</span></p>
</sign-up-in-form>
<sign-up-in-form v-show="changePassword">
 
  <password-checker :password="passwordChange" :input-strength="inputCheck">
    <input-sign class="input-check" type="password" v-model:passwordNew="passwordChange" placeholder="Password"/>
    </password-checker>
    
  <input-sign type="password" placeholder="Confirm Password"></input-sign>
  <app-button-sign >Change Password</app-button-sign>
</sign-up-in-form>
</template>

<style>

* {
margin: 0;
padding: 0;
}

.nav-bar{
position: fixed;
z-index: 1;
justify-content: flex-end;
display: flex;
min-width: 100%;
background-color: rgba(255,255,255,0.5);
padding-bottom: 10px;
}

.main_sign-in{
  display: flex;
  gap: 15px;
}
.modal-hello{
  position: fixed;
  display: flex;
justify-content: center;
align-items: center;
width: 100%;
top: 250px;
z-index: 20;
 
  
}
.modal-hello-item{
  background-color: #fff;
  border:2px solid  #F79E89 ;
 min-width: 400px;
 min-height: 200px;
 display: flex;
 align-items: center;
 justify-content: center;
 border-radius: 20px;
 
}
.modal-hello-text{
  font-family: Montserrat, sans-serif;
  color: #F79E89;
  font-weight: 600;
  font-size: 70px;
  letter-spacing: 2px;
  
}
.v-enter-active,
.v-leave-active {
  transition: opacity 1s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

.sign-text span{
color: #F79E89;
cursor: pointer;
}

.sign-text{
  color: #27272780;
  font-family:Montserrat;
  margin-top: 10px;
  font-size: 10px;
  text-align: center;
}
.sign_forgot{
  text-align: end;
}
.input-check{
  margin-bottom: 5px;
}
a{
  text-decoration-line: none;
  color:#27272780; 
 
}
.input-eye__block{
 display: flex; 
 align-items: center;
}
.input-check__icon{
  margin-left: -35px;
  margin-bottom: -15px;
}
.input-check__icon2 {
margin-bottom: -22px;
}
</style>
