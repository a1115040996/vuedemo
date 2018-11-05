<template>
  <div @click="handleClick">
    {{childMessage.msg.name}}
    <div @click="handleSendMsg">点击子类执行父类方法</div>
  </div>
</template>
<script>
    export default {
        name: "child",
        data:function(){
          return{
            name:'我是子组件'
          }
        },
        methods:{
          handleClick:function(){
            console.log(this.childFunctin);
          },
          handleSendMsg:function(){
            this.childFunctin.sayHi({
              name:'子集传递的数据',
              content:'hello i am max'
            })
          }
        },
      props:{
        childMessage:Object,
        childFunctin:Object
      }
    }
</script>

<style scoped>

</style>
