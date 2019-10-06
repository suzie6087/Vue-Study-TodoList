<template>
  <div id="app">
    <!--각 컴포넌트들을 사용할 수 있게 태그들을 등록시켜준다. -->
    <TodoHeader></TodoHeader>
    <TodoInput></TodoInput>
    <TodoList></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
// 컴포넌트들을 import해줘야 상위컴포넌트에서 사용이 가능하다.  
import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
import TodoFooter from './components/TodoFooter.vue'

export default {
  components: {
   'TodoHeader':TodoHeader,
   'TodoInput':TodoInput,
   'TodoList':TodoList,
   'TodoFooter':TodoFooter
  },
}
</script>

<style>
 body{
   text-align: center;
   background-color: #f6f6f6;
 }
 input{
   border-style: groove;
   width:200px;
 }
 button{
   border-style: groove;
 }
 .shadow{
   box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03)
 }
</style>
