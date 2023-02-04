<template>
    <input class="input_sign" type="text" placeholder="Email" :value="passwordNew" @input="inputSign"/>
</template>
<script>
export default{
    name:'input-sign',
    props:{
        passwordNew:String
    },
    methods:{
        inputSign(event){
         this.$emit('update:passwordNew',event.target.value)
        }
    }
}
</script>
<style>
.input_sign{
    display: block;
  border:1px solid #27272780;
  width: 300px;
  height: 20px;
  margin-top: 20px;
  border-radius: 10px;
  padding: 8px;
  font-family: Montserrat;
  color: #27272780;
  font-size: 14px;
  
  }
</style>