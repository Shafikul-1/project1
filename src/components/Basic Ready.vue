<script setup>
import { ref } from 'vue'

const outputArea = ref('')
const inputArea = ref('')
const inputFeture = ref('')
const inputValueSearch = ref('')
let fastFetureInput = ref(false)
let fastFetureOutput = ref(false)

// Input Remove Call
const symbol = ref(false)
const number = ref(false)
const text = ref(false)
const other2 = ref(false)
const other3 = ref(false)
const other4 = ref(false)
 
//====================================
// Sumnit Function
function submitFn(){
  let result = inputArea.value;

  if(symbol.value){
    result = result.replace(/[^\w\s]/g, '') 
  }
  if(number.value){
    result = result.replace(/\d/g, '') 
  }
  if(text.value){
    result = result.replace(/[a-zA-Z]/g, '') 
  }
  if(other2.value){
    result = result.replace(/\d/g, '')
  }
  if(other3.value){
    result = result.replace(/\d/g, '')
  }
  if(other4.value){
    result = result.replace(/\d/g, '')
  }

  outputArea.value = result; 
}
// Reset Function
function resetFn (){
  inputArea.value = ''
}

//All Selected Function
function allSelect(){
  const outputTextarea = document.getElementById('outputTextarea');
  outputTextarea.select();
}
function copyAll(){
  const outputTextarea = document.getElementById('outputTextarea');
  outputTextarea.select();
  document.execCommand('copy');
}
// Input feture all hide and show 
 function featureHideInput(){
  fastFetureInput.value = !fastFetureInput.value
 }
//Output  feture all hide and show 
function featureHideOutput(){
  fastFetureOutput.value = !fastFetureOutput.value
}
</script>

<template>

  <!-- Input Section -->
<div class="inputSec">
  <div class="flex ">
    <div class="w-1/3 bg-gray-100 mx-3 py-2 px-4 rounded-md md:my-3">
      <h1 class="font-bold text-4xl text-center">All Feature Here </h1>
      <div class="flex mt-4">
        <i @click="featureHideInput()" class="fa-solid fa-bars text-4xl font-bold cursor-pointer" :class="fastFetureInput == true ? 'fa-xmark' : 'fa-bars'"></i>
        <div class="relative w-10/12">
          <div class="absolute bg-gray-400 rounded-md p-3 ml-3 w-full overflow-auto h-[16rem]" v-show="fastFetureInput">
            <!-- All Teature Add -->
              <ul class=" w-full text-sm font-medium text-gray-900 bg-white border border-gray-200 rounded-lg dark:bg-gray-700 dark:border-gray-600 dark:text-white">
                  <li class="cursor-pointer w-full border-b border-gray-200 rounded-t-lg dark:border-gray-600">
                      <div class="flex items-center pl-3 ">
                          <input v-model="symbol" id="symbol-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                          <label for="symbol-checkbox" class="capitalize w-full py-3 ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">remove symbol</label>
                      </div>
                  </li>
                  <li class="w-full border-b border-gray-200 rounded-t-lg dark:border-gray-600">
                      <div class="flex items-center pl-3">
                          <input v-model="number" id="number-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                          <label for="number-checkbox" class="capitalize w-full py-3 ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">remove number</label>
                      </div>
                  </li>
                  <li class="w-full border-b border-gray-200 rounded-t-lg dark:border-gray-600">
                      <div class="flex items-center pl-3">
                          <input v-model="text" id="other1-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                          <label for="other1-checkbox" class="capitalize w-full py-3 ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">remove text</label>
                      </div>
                  </li>
                  <li class="w-full border-b border-gray-200 rounded-t-lg dark:border-gray-600">
                      <div class="flex items-center pl-3">
                          <input v-model="other2" id="other2-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                          <label for="other2-checkbox" class="capitalize w-full py-3 ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">remove ...</label>
                      </div>
                  </li>
                  <li class="w-full border-b border-gray-200 rounded-t-lg dark:border-gray-600">
                      <div class="flex items-center pl-3">
                          <input v-model="other3" id="other3-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                          <label for="other3-checkbox" class="capitalize w-full py-3 ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">remove ...</label>
                      </div>
                  </li>
                  <li class="w-full border-b border-gray-200 rounded-t-lg dark:border-gray-600">
                      <div class="flex items-center pl-3">
                          <input v-model="other4" id="other4-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                          <label for="other4-checkbox" class="capitalize w-full py-3 ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">remove ...</label>
                      </div>
                  </li>
              </ul>
          </div>
          <!-- All Reature Back Text -->
          <div class="ml-7">
            <code>If you want to see all the features, click on the 3 dot button and enjoy all the features. <br>
              I feel blessed to be able to help you. But don't forget to let us know your feedback. <br>
              Let us know your more views… 
            </code>
          </div>
        </div>
      </div>
    </div>
    <div class="bg-gray-200 w-1/3 mx-3 py-2 px-4 rounded-md md:my-3">
      <label for="input" class="font-bold text-2xl ">Input Your Text Here</label>
      <textarea v-model="inputArea" name="" id="" cols="" rows="10" placeholder="Enter Your Text " class="mt-3 w-full rounded-md focus:outline-none p-3"></textarea>
    </div>
    
    <div class="bg-gray-300 w-1/3 mx-3 py-2 px-4 rounded-md md:my-3"> 
      <!-- Reset And Submit Function -->
      <ul class="flex flex-row gap-4">
        <li :name="inputFeture" @click="resetFn()" class="grow  capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer">reset</li> 
        <li :name="inputFeture" @click="submitFn()" class="grow  capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer">Submit</li>
      </ul>
    </div>
  </div>
</div>

<!-- OutPut Section -->

<div class="ouputSec flex">
  <div class="w-1/3 bg-gray-100 mx-3 py-2 px-4 rounded-md md:my-3">
      <h1 class="font-bold text-4xl text-center">Second Feature Here </h1>
      <div class="flex mt-4">
        <i @click="featureHideOutput()" class="fa-solid fa-bars text-4xl font-bold cursor-pointer" :class="fastFetureOutput == true ? 'fa-xmark' : 'fa-bars'"></i>
        <div class="relative w-10/12">
          <div class="absolute bg-gray-400 rounded-md p-3 ml-3 w-full overflow-auto h-[16rem]" v-show="fastFetureOutput">
            <!-- All Teature Add -->
              <ul class=" w-full text-sm font-medium text-gray-900 bg-white border border-gray-200 rounded-lg dark:bg-gray-700 dark:border-gray-600 dark:text-white">
                  <li class="cursor-pointer w-full border-b border-gray-200 rounded-t-lg dark:border-gray-600">
                      <div class="flex items-center pl-3 ">
                          <input id="symbol-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                          <label for="symbol-checkbox" class="capitalize w-full py-3 ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">remove symbol</label>
                      </div>
                  </li>
                  <li class="w-full border-b border-gray-200 rounded-t-lg dark:border-gray-600">
                      <div class="flex items-center pl-3">
                          <input id="number-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                          <label for="number-checkbox" class="capitalize w-full py-3 ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">remove number</label>
                      </div>
                  </li>
                  <li class="w-full border-b border-gray-200 rounded-t-lg dark:border-gray-600">
                      <div class="flex items-center pl-3">
                          <input id="other1-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                          <label for="other1-checkbox" class="capitalize w-full py-3 ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">remove ...</label>
                      </div>
                  </li>
                  <li class="w-full border-b border-gray-200 rounded-t-lg dark:border-gray-600">
                      <div class="flex items-center pl-3">
                          <input id="other2-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                          <label for="other2-checkbox" class="capitalize w-full py-3 ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">remove ...</label>
                      </div>
                  </li>
                  <li class="w-full border-b border-gray-200 rounded-t-lg dark:border-gray-600">
                      <div class="flex items-center pl-3">
                          <input id="other3-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                          <label for="other3-checkbox" class="capitalize w-full py-3 ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">remove ...</label>
                      </div>
                  </li>
                  <li class="w-full border-b border-gray-200 rounded-t-lg dark:border-gray-600">
                      <div class="flex items-center pl-3">
                          <input id="other4-checkbox" type="checkbox" value="" class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-700 dark:focus:ring-offset-gray-700 focus:ring-2 dark:bg-gray-600 dark:border-gray-500">
                          <label for="other4-checkbox" class="capitalize w-full py-3 ml-2 text-sm font-medium text-gray-900 dark:text-gray-300">remove ...</label>
                      </div>
                  </li>
              </ul>
          </div>
          <!-- All Reature Back Text -->
          <div class="ml-7">
            <code>If you want to see all the features, click on the 3 dot button and enjoy all the features. <br>
              I feel blessed to be able to help you. But don't forget to let us know your feedback. <br>
              Let us know your more views… 
            </code>
          </div>
        </div>
      </div>
    </div>

  <div class="bg-gray-300 w-1/3 mx-3 py-2 px-4 rounded-md md:my-3">
    <label for="outPut" class="font-bold text-2xl">Our Text Output Here</label>
    <textarea v-model="outputArea" class="mt-3 w-full rounded-md focus:outline-none p-3" placeholder="Your Ouput" name="" id="outputTextarea" cols="" rows="10"></textarea>
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
      <li @click="allSelect()" class="capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer" id="outputArea">Select All</li>
      <li class="capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer" @click="copyAll()">All Copy</li>
    </ul>
  </div>
</div>

</template>

<style scoped>

</style>