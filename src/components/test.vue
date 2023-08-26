<!-- <template>
    <div>
      
      <ul>
        <li>
          <input id="symbol-checkbox" type="checkbox" v-model="removeSymbol"/>
          <label for="symbol-checkbox">Remove Symbol</label>
        </li>
        <li>
          <input
            id="number-checkbox"
            type="checkbox"
            v-model="removeNumber"
          />
          <label for="number-checkbox">Remove Number</label>
        </li>
        <li>
          <input
            id="text-checkbox"
            type="checkbox"
            v-model="removeText"
          />
          <label for="text-checkbox">Remove Text</label>
        </li>
      </ul>
  
      
      <textarea
        v-model="inputArea"
        class="border-4"
        cols="30"
        rows="10"
      ></textarea>
      <button class="border-4" @click="complete">Submit</button>
  
      
      <textarea
        v-model="outputArea"
        class="border-4"
        cols="30"
        rows="10"
      ></textarea>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const inputArea = ref('');
  const outputArea = ref('');
  const removeSymbol = ref(false);
  const removeNumber = ref(false);
  const removeText = ref(false);
  
  function complete() {
    let result = inputArea.value;
  
    if (removeSymbol.value) {
      result = result.replace(/[^\w\s]/g, '');
    }
  
    if (removeNumber.value) {
      result = result.replace(/\d/g, '');
    }
  
    if (removeText.value) {
      result = result.replace(/[a-zA-Z]/g, '');
    }
  
    outputArea.value = result;
  }
  </script>
   -->
<!-- 
   <script setup>
import { ref } from 'vue'

const inputArea = ref('')
const outputArea = ref('')
const selectedOptions = ref([])

const symbol = () => {
  inputArea.value = inputArea.value.replace(/[^\w\s]/g, '')
}

const numbers = () => {
  inputArea.value = inputArea.value.replace(/\d/g, '')
}

const text = () => {
  inputArea.value = inputArea.value.replace(/[a-zA-Z]/g, '')
}

const complete = () => {
  selectedOptions.value.forEach((option) => {
    switch (option) {
      case 'symbol':
        symbol()
        break
      case 'numbers':
        numbers()
        break
      case 'text':
        text()
        break
    }
  })

  outputArea.value = inputArea.value
}
</script>

<template>
  <div>
    <ul>
      <li>
        <input type="checkbox" id="symbol-checkbox" v-model="selectedOptions" value="symbol">
        <label for="symbol-checkbox">Remove symbols</label>
      </li>
      <li>
        <input type="checkbox" id="number-checkbox" v-model="selectedOptions" value="numbers">
        <label for="number-checkbox">Remove numbers</label>
      </li>
      <li>
        <input type="checkbox" id="text-checkbox" v-model="selectedOptions" value="text">
        <label for="text-checkbox">Remove text</label>
      </li>
    </ul>

    <textarea v-model="inputArea" name="" class="border-4" id="" cols="30" rows="10"></textarea>
    <button class="border-4" @click="complete()">Submit</button>

    <textarea v-model="outputArea" name="" class="border-4" id="" cols="30" rows="10"></textarea>
  </div>
</template> -->
