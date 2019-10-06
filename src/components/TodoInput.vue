<!--할 일 입력 및 추가하는 컴포넌트  -->
<template>
    <div>
        <input type="text" v-model="newTodoitem" /> <!-- 데이터의 양반향 소통이 있어야함으로 v-model을 써서 바인딩 해준다. -->
        <button @click="addTodo" >추가</button> <!--버튼을 클릭했을때 이벤트를 주는 함수를 넣는다. v-on=>@ 대체 가능  -->
    </div>
</template>

<script>
    export default {
    /* 양방향으로 통신이 가능하다. 인풋에 입력을 하면,  newTodoItem에 값이 들어간다. 
    data() {
           return {
               newTodoItem:"" 
           }
       },
       */
      methods: {
          addTodo() {
              console.log(this.newTodoitem); // 클릭 이벤트로 인풋에 담긴 newTodoitem이 콘솔에 찍힌다. 
          }
      },
    }
</script>

<style>

</style>
