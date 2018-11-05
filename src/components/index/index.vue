<template>
  <div>
    {{name}}
    <chi :childMessage="childMessage" :childFunctin="childFunctin"></chi>

    <div id="clickme" @click="sendMessageForChild">点击我 向子组件传递数据</div>

    <div >{{childMessage.handle.name}} ---  {{childMessage.handle.content}}</div>
  </div>
</template>

<script>
  import chi from '@/components/index/components/child';
    export default {
        name: "index",
        data:function(){
          return {
            name:'hello world',
            index:0,
            childMessage:{
              msg:{
                name:'zhangsan',
                age:18
              },
              handle:{
                name:'',
                content:''
              }
            },
            childFunctin:{
              sayHi:function(msg){
                this.childMessage.handle = msg;
              }.bind(this)
            }
          }
        },
        methods:{
          sendMessageForChild:function(){
            this.index+=1;
            console.log('点击执行')
            this.childMessage.msg.name = '下标值相累加'+this.index;
          }
        },
      components: { chi : chi },
    }
</script>

<style scoped>

</style>
