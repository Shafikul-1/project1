<script setup>
import { ref } from 'vue'

const inputFeture = ref('')
const inputArea = ref('')
let fastFetureInput = ref(false)
function removeNumber(){
  const correctionValue = inputArea.value.replace(/\d/g, '')
  outputArea.value = correctionValue
}

// Sumnit Function
function submitFn(){
  outputArea.value = inputArea.value
  // alert('Clicked Submit Btn')
}
// Reset Function
function resetFn (){
  inputArea.value = ''
}


//Remove Symbol Function
function removeSymbol(){
  const correctionValue = inputArea.value.replace(/[^\w\s]/g, '')
  outputArea.value = correctionValue
  // /[^\w\s]|_/g, ''
// /[^\w\s]/g, ''
}
// Input feture all hide and show 
function featureHideInput(){
  fastFetureInput.value = !fastFetureInput.value
 }
</script>

<template>
    
  <!--Fast Input Section -->
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
        <div class="bg-gray-200 w-1/3 mx-3 py-2 px-4 rounded-md md:my-3">
        <label for="input" class="font-bold text-2xl ">Input Your Text Here</label>
        <textarea v-model="inputArea" name="" id="" cols="" rows="10" placeholder="Enter Your Text " class="mt-3 w-full rounded-md focus:outline-none p-3"></textarea>
        </div>
        <div class="bg-gray-300 w-1/3 mx-3 py-2 px-4 rounded-md md:my-3">
        <!--  -->
        <ul>
            <li :name="inputFeture" @click="resetFn()" class="capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer">reset</li>
            <li :name="inputFeture" @click="removeNumber()" class="capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer">Remove Number</li>
            <li :name="inputFeture" @click="removeSymbol()" class="capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer">Remove Symbol</li>
            <li :name="inputFeture" class="capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer">Remove symbol</li>
            <li :name="inputFeture" @click="submitFn()" class="capitalize  font-bold text-md bg-black text-white my-2 py-1 pl-3 rounded hover:bg-green-600 transition-all cursor-pointer">Submit</li>
        </ul>
        </div>
    </div>
    </div>


</template>

<style scoped>

</style>