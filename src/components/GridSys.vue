<template>
    <div>
        <div class="flex gap-1 w-3/4" >
            <div class="box1 grow w-[200px] p-7 rounded-md bg-blue-600">1</div>
            <div class="box2 grow w-[400px] p-7 rounded-md bg-blue-600">2</div>
            <div class="box3 shrink w-[300px] p-7 rounded-md bg-blue-600">3</div>

        </div>
        <div class="bg-black text-white "   >{{ count }}</div>
        <button class="" @click="count++">click ME</button>
    </div>
</template>

<script setup >

import {ref} from 'vue';
const count = ref(0);
</script>

<style  scoped>

</style>