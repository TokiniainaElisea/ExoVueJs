<script setup>
import {ref} from 'vue'
const dataList = ref([])
const stat = ref(true)

//show or hide list
function showHide(){
  stat.value = !stat.value
}

//push
function pushNumber(){
   dataList.value.push(dataList.value.length +1)
}

//pop
function popNumber(){
  dataList.value.pop()
}

//reverse
function reverseList(){
  dataList.value.reverse()
}
</script>

<template>
    <div class="boutton">
        <button v-if="stat" @click="showHide"> Hide </button>
        <button v-else @click="showHide"> Show </button>
        <button @click="pushNumber"> Push number </button>
        <button @click="popNumber"> Pop number </button>
        <button @click="reverseList"> Reverse list </button>
    </div>
    <div class="list" v-if="stat && dataList.length"> 
        
          <p v-for="list in dataList"> {{list}}</p>
        
    </div>
    <div class="list" v-else-if="dataList.length ==0">
       <p> No data :( </p>
    </div>
    <div class="list" v-else>
      <p> List is hidden :p </p>
    </div>
</template>

<style>

.boutton{
  text-align : center;
}

.list{
  text-align: center;
}

button{
  width : 100px;
  height : 30px;
  background-color: black;
  margin : 2px;
  color : #ffffff;
  border-radius: 5px;
  font-size: 13px;
}

button:hover{
  color: black;
  background-color: #ffffff;
}

p{
  color : #ffffff;
  border: 1px black solid;
  border-radius: 3px;
  background-color: black;
  font-weight: bold;
  width : 250px;
  margin : 4px auto;
}

li{
  color : lightgreen;
}
</style>