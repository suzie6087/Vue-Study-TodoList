<!--할 일 입력 및 추가하는 컴포넌트  -->
<template>
    <div class="inputBox shadow">
        <input type="text" v-model="newTodoItem" @keyup.enter="addTodo" /> <!-- 데이터의 양반향 소통이 있어야함으로 v-model을 써서 바인딩 해준다. -->
        <!-- <button @click="addTodo" >추가</button> --><!--버튼을 클릭했을때 이벤트를 주는 함수를 넣는다. v-on=>@ 대체 가능  -->
        <span class="addContainer" @click="addTodo">
            <i class="fas fa-plus addBtn"></i>
        </span>
    </div>
</template>

<script>
    export default {
    /* 양방향으로 통신이 가능하다. 인풋에 입력을 하면,  newTodoItem에 값이 들어간다. */
      data:function() {
        return {
            newTodoItem: ""
        }
    },
      methods: {
          addTodo:function() {
             // console.log(this.newTodoitem); // 클릭 이벤트로 인풋에 담긴 newTodoitem이 콘솔에 찍힌다. 
            if(this.newTodoItem !== ''){ // newTodoItem이 비어있지 않다면 
                  localStorage.setItem(this.newTodoItem, this.newTodoItem);  // localStorage에 저장한다. 정보들을 임시저장한다 크롬 개발자도구에서 확인가능하다. 
                  this.clearInput(); // 정보를 localStorage에 저장하고 input창을 비워준다.
            } 
            
          },
          clearInput:function(){
              this.newTodoItem = ''; // 입력창 비워주기 
          }
      },
    }
</script>

<style scoped>
 input{
     outline: none;
 }
 .inputBox{
     background: white;
     height: 50px;
     line-height: 50px;
     border-radius: 5px;
 }
 .inputBox input{
     border-style: none;
     font-size: 0.9rem;
 }
 .addContainer{
     float: right;
     background: linear-gradient(to right, #6478FB, #8763FB);
     display: block;
     width: 3rem;
     border-radius: 0 5px 5px 0;
 }
 .addBtn{
     color: white;
     vertical-align: middle;
 }
</style>
