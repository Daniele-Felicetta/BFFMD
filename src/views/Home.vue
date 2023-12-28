<template>
    <div id="wrapper" class="h-screen">
        <div class="examples">
            <Examples />
        </div>
        <div class="compiler">
            <Compiler />
        </div>
        <div>
            <AsciiTable>
                
            </AsciiTable>
        </div>
    </div>
</template>
<script setup>
import Compiler from '@/components/Compiler.vue';
import Examples from '@/components/Examples.vue';
import AsciiTable from '@/components/AsciiTable.vue';
</script>
<style scoped>
    #wrapper {
        display: grid;
        grid-template-columns: 2fr 1fr 2fr; 
    }
    .compiler {
        z-index: 1;
    }
    .examples {
        z-index: 20;
    }
</style>