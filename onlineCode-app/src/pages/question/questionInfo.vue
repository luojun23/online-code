<template>
    <view>{{ person.name }}</view>
    <button @click="change2">修改年龄</button>
    <button @click="change">修改</button>
    <button @click="change1">修改名字</button>
</template>

<script setup>
import { reactive, ref ,toRefs,watch} from 'vue';

let person = reactive({name:'luojun',age:18})
const change1 = ()=>{
    person.name+='~'
}
const change2 = ()=>{
    person.age+=1
}
const change = ()=>{
    Object.assign(person,{name:'zhangsan',age:20})
}
watch(()=>person.name,(newVal,oldVal)=>{
    console.log(newVal,oldVal)
})

</script>
