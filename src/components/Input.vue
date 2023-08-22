<script setup>
import { ref, reactive } from 'vue'

const outputArea = ref('')
const inputArea = ref('')
const inputFeture = ref('')
const inputValueSearch = ref('')
// Sumnit Function
function submitLi(){
  outputArea.value = inputArea.value
  // alert('Clicked Submit Btn')
}
// Reset Function
function resetLi (){
  inputArea.value = ''
}

//Number Remove Function
function removeNumber(){
  const correctionValue = inputArea.value.replace(/\d/g, '')
  outputArea.value = correctionValue
}

//Remove Symbol Function
function removeSymbol(){
  const correctionValue = inputArea.value.replace(/[^\w\s]/g, '')
  outputArea.value = correctionValue

  // /[^\w\s]|_/g, ''
// /[^\w\s]/g, ''
}


</script>

<template>

  <!-- Input Section -->
<div class="inputSec">
  <div class="flex ">
    <div class="w-1/3 bg-gray-100 mx-3 py-2 px-4 rounded-md md:my-3">
      <h1 class="font-bold text-4xl text-center">All Text Section</h1>
      <div class="flex">
        <img src="https://img.icons8.com/?size=2x&id=63781&format=png" alt="">
        <div class=""></div>
      </div>
    </div>
    <div class="bg-gray-200 w-1/3 mx-3 py-2 px-4 rounded-md md:my-3">
      <label for="input" class="font-bold text-2xl ">Input Your Text Here</label>
      <textarea v-model="inputArea" name="" id="" cols="" rows="10" placeholder="Enter Your Text " class="mt-3 w-full rounded-md focus:outline-none p-3"></textarea>
    </div>
    <div class="bg-gray-300 w-1/3 mx-3 py-2 px-4 rounded-md md:my-3">
      <!--  -->
      <ul>
        <li :name="inputFeture" @click="resetLi" class="capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer">reset</li>
        <li :name="inputFeture" @click="removeNumber()" class="capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer">Remove Number</li>
        <li :name="inputFeture" @click="removeSymbol()" class="capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer">Remove Symbol</li>
        <li :name="inputFeture" class="capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer">Remove symbol</li>
        <li :name="inputFeture" @click="submitLi" class="capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer">Submit</li>
      </ul>
    </div>
  </div>
</div>





<!-- OutPut Section -->

<div class="ouputSec flex">
  <div class="bg-gray-300 w-1/3 mx-3 py-2 px-4 rounded-md md:my-3">
    <h3>Text Section</h3>
  </div>
  <div class="bg-gray-300 w-1/3 mx-3 py-2 px-4 rounded-md md:my-3">
    <label for="outPut" class="font-bold text-2xl">Our Text Output Here</label>
    <textarea @click="" v-model="outputArea" class="mt-3 w-full rounded-md focus:outline-none p-3" placeholder="Your Ouput" name="" id="" cols="" rows="10"></textarea>
  </div>
  <div class="bg-gray-300 w-1/3 mx-3 py-2 px-4 rounded-md md:my-3">
    <p>Feture Sec</p>
    <!-- Input Filter Area -->
    <form @submit.prevent>   
          <label for="default-search" class="mb-2 text-sm font-medium text-gray-900 sr-only dark:text-white">Search</label>
          <div class="relative">
              <div class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
                <svg class="w-4 h-4 text-gray-500 dark:text-gray-400" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 20 20"> <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m19 19-4-4m0-7A7 7 0 1 1 1 8a7 7 0 0 1 14 0Z"/> </svg>
              </div>
              <input v-model="inputValueSearch" type="search" id="default-search" class="block w-full p-4 pl-10 text-sm text-gray-900 border border-gray-300 rounded-lg bg-gray-50 focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="Enter Your Search Text" required>
              <button @click="generateOutput" type="submit" class="text-white absolute right-2.5 bottom-2.5 bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-4 py-2 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">Search</button>
          </div>
      </form> 
      <!--  -->
    <ul>
      <li class="capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer">Select All</li>
      <li class="capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer">All Copy</li>
    </ul>
  </div>
</div>

</template>

<style scoped>

</style>