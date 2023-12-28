<template>
    <div class="all h-75" >
        <h1> Compiler BF </h1>
        <v-form action="" @submit.prevent="compile">
            <v-textarea  auto-grow
        style="width: 60vw;"
        color="deep-purple"
        class="textarea"
        
        cols="20" v-model="stringProgram" 
        label="Write a Program"></v-textarea>
            <br>
            <v-btn @click="compile">Compile</v-btn>
        </v-form>
        <div class="buttons">
            <v-btn @click="concatString('+')">+</v-btn>
            <v-btn @click="concatString('-')">-</v-btn>
            <v-btn @click="concatString('>')">></v-btn>
            <v-btn @click="concatString('<')">&lt</v-btn>
            <v-btn @click="concatString('[')">[</v-btn>
            <v-btn @click="concatString(']')">]</v-btn>
            <v-btn @click="concatString('.')">.</v-btn>
        </div>
        <h2>{{resultCompile}}</h2>
    </div>
</template>
<script setup>
import {ref} from 'vue';
import compiler from '../compiler.js';
let stringProgram = ref('');
let resultCompile =ref('')

const concatString= (str)=>{
    console.log(str)
    stringProgram.value+=str;
}
const compile = ()=>{
    console.log(stringProgram.value)
   resultCompile.value=compiler(stringProgram.value);
}

</script>

<style scoped>
    .textarea{

    }
    aside{
        position: absolute;
        top: 0rem;
        left: 0rem;
    }
    aside button{
        padding: 20px;
        margin: 2rem;
        
    }
    .buttons{
        display: flex;
        justify-content: center;
        gap: 1rem;
        z-index: 0;
    }

 
    .all{
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;
        gap: 4rem;
    }
    .v-field{
        width: 1000px;
    }
    .all>textarea{
        width: 100%;
    }
    input{
        padding: 5px;
        border-radius: 5px;
        background-color: rgb(74, 74, 74);
        color: white;
        font-size: 20px;
    }
    form{
        display: flex ;
        justify-content: space-between;
        flex-direction: column;
        align-items: center;
        gap: 10px;
    }
  
</style>