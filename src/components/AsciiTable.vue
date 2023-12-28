<template>
    <div class="bar " v-if="!showAscii">
        <v-toolbar class="bar  rounded-lg">
          <v-btn class="rounded-lg p-10" @click="()=>showAscii = !showAscii">Ascii</v-btn>
        </v-toolbar>
    </div>
    <div v-else class="bar2" >

    <v-page v-model="thePage"   class="example rounded-lg bar2" :height="800" width="900" elevation="20"
    style="resize: horizontal;overflow: auto" >
            <v-btn @click="()=>showAscii = !showAscii" class="rounded-s-xl"><v-icon icon="mdi-close-circle"></v-icon></v-btn>
        <v-page :height="740" width="900"  class="table-wrapper overflow-auto">
            <Table class="table-wrapper"></Table>
        </v-page>
    </v-page>
</div>
    
</template>
<script setup>
import {ref} from 'vue';
import Table from './Table.vue';
const showAscii= ref(false)
</script>
<style scoped>
#wrapper table {
    margin-bottom: 5px;
}
    .bar{
      width: 7rem;
      position: absolute;
      top: 0;
      right: 0;
    }
    .bar2{
    position: absolute;
      top: 0;
      right: 0;
      display: flex;
      flex-direction: row-reverse;
      justify-content: space-between;
      background-color: white;
    }
    .table-wrapper{
        width: 500px;
        height: 700px;
        background-color: white;

    }
  button{
        z-index: 200;
    }
   
</style>
<style>
.v-table__wrapper{
    z-index: 20;
}

</style>