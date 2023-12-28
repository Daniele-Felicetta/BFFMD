<template>
    <div class="bar" v-if="showExamples">
        <v-toolbar class="bar  rounded-lg">
          <v-btn class="rounded-lg p-10" @click="()=>showExamples = !showExamples">Examples</v-btn>
        </v-toolbar>
    </div>
    
    <v-sheet v-model="thePage"  v-else class="example rounded-lg" :height="800" width="900" elevation="20"
    style="resize: horizontal;overflow: auto; "
    >
      <v-sheet :height="740" width="900" elevation="0"  class=" overflow-auto">
        <div class="d-flex mb-5" style="gap:30px">
          <v-btn @click="()=>showExamples = !showExamples" class="rounded-e-xl"><v-icon icon="mdi-close-circle"></v-icon></v-btn>
          <h1>{{examples[page-1].title}}</h1>
        </div>
        <p class="ml-3"> 
          <span class=" font-weight-black">Raw: </span>
          <span> {{examples[page-1].raw}}</span>
        </p>
        <br>
        <br>
        <pre class="ml-4">{{examples[page-1].explained}}</pre>
        <v-icon icon="fa:fas fa-circle-notch fa-spin"></v-icon>
      </v-sheet>
       <div style="position:fixed; width: 900px">
          <v-pagination v-model="page" :length="examples.length"></v-pagination>
        </div>

    </v-sheet>
</template>
<script setup>
import examples from "../examples/examples.js";
import {ref,watch} from 'vue';
const showExamples = ref(true)
const page = ref(1);
const thePage = ref(0);
watch(page,() => {


})
</script>
<style scoped >
.bar{
      width: 10rem;
     
    }
    .example{
      z-index: 200!important;
      width: 400px;
      word-wrap: break-word;
      word-break: break-all;
    }
    .examples{
      resize: horizontal;
    }
</style>
<style>

*::-webkit-scrollbar {
  width: 15px;
}

*::-webkit-scrollbar-track {
  background: #e6e6e6;
  border-left: 1px solid #dadada;
  border-radius: 8px;
}

*::-webkit-scrollbar-thumb {
  background: #b0b0b0;
  border: solid 3px #e6e6e6;
  border-radius: 7px;
}

*::-webkit-scrollbar-thumb:hover {
  background: black;
}


</style>