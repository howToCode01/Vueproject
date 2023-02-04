<template>
<button class="app_button">
    <slot>SIGN IN</slot>
</button>
</template>
<script>
export default{
    name:'app-button'
}
</script>
<style>
    .app_button{
        padding: 15px;
       justify-self: flex-end;
        background-color: #F79E89;
        border-radius: 12px;
        margin-top: 10px;
        margin-right: 10px;
        max-width: 100px;
        font-size: 14px;
        font-weight: 400;
        font-family: Montserrat, sans-serif;
        color: #fff;
        border-style: hidden;
        transition: all 1s ease-out;

      }  
      .app_button:hover{
   transform: translate(5px);
   opacity: 0.7;
      }
      
</style>