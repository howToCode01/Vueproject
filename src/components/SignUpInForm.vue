<template>
    <div class="signUp">
        <div class="signUp-content">
        <div class="signUp-item">
          <div class="signUp-icon">
        <img src="../images/Union.svg" alt="" class="signUp-img">
          </div>
        </div>
        <div class="signUp-item">
        <slot></slot>
        </div>
        </div>
        </div>
</template>
<script>
export default{
    name:'sign-up-in-form'
}
</script>
<style>
.signUp{
    display: flex; 
    justify-content: center;
    align-items: center;
    
  
  }
  .signUp-content{
    margin-top: 68px;
  background-color: #fff;
  border:1px solid #F79E89;
  border-radius: 10px;
  padding: 50px 100px 15px 100px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
  }
  .signUp-item{
   margin-bottom: 30px;
  }
</style>