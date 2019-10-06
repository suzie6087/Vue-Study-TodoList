<!--할 일 목룍 표시, 특정 할 일 삭제하는 컴포넌트 -->
<template>
    <div>
        <ul>
            <li v-for="todoItem in todoItems" v-bind:key="todoItem"> 
                <!--v-bind:key="todoItem": 만약에 반복문에 바인딩 된 애들이 
                값이 변경이 되었을때, 반복문 전체를 그리지 않고 변경된 놈만 새로 그려주기위한 key를 주는 것이다. 
            -->
                {{todoItem}}

            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        data:function() {
            return {
                todoItems:[] // todo값들을 담을 배열 생성 
            }
        },
        /* life 사이클 method   */
        /* localStorage에 담긴 값들을 뷰에 출력   */
        /* Created() 라이프 사이클 메서드에 for문과 push()로 로컬스토리지의 모든 데이터를 todoUtems에 저장하는 로직 구현  */
        created:function(){
            if(localStorage.length > 0 ){
                for(var i = 0 ; i < localStorage.length ; i++){
                    this.todoItems.push(localStorage.key(i)); // 배열에 넣기 
                }
            }
        }
    }
</script>

<style scoped>
    ul{
        list-style-type: none;
        padding-left: 0px;
        margin-top: 0;
        text-align: left;
    }
    li{
        display: flex;
        min-height: 50px;
        height: 50px;
        line-height: 50px;
        margin:0.5rem 0;
        padding: 0 0.9rem;
        background: white;
        border-radius: 5px;
    }
    .removeBtn{
        margin-left: auto;
        color: #de4343;
    }
    .checkBtnCompleted{
        color: #b3adad;
    }
    .textCompleted{
        text-decoration:line-through;
        color:#b3adad; 
    }
</style>
