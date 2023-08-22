<template>
    <textarea name="" v-model="input" id="" cols="30" rows="10"></textarea>
    <button @click="remove()"> Remove number</button>
    <textarea name="" v-model="output" id="" cols="30" rows="10"></textarea>
</template>
<script setup>
import { ref } from 'vue'
const input = ref('')
const output = ref('')
function remove(){
    const correctionValue = input.value.replace(/[0-9]/g, '');
    output.value = correctionValue;
}
</script>
 