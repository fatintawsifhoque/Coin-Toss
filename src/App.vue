<template>
 <section class="h-screen w-screen bg-amber-100 flex flex-col items-center justify-center p-4">
  <h1 class="text-6xl md:text-8xl font-black text-center">Toss</h1>
  
  <div class="h-100px w-100px rounded-full border border-black mt-8 overflow-hidden">
    <img :src="'/' + output + '.png'" alt="coin" class="h-full w-full object-cover">
  </div>
  
  <div v-if="r" class="mt-6 text-center">
    <p class="text-xl md:text-2xl font-bold">
      Result of this toss is <span class="capitalize">"{{ output }}"</span>
    </p>
  </div>
  
  <button 
    @click="select" 
    class="mt-8 font-bold text-xl md:text-2xl border border-black rounded-2xl px-6 py-3 cursor-pointer hover:bg-amber-900 hover:text-white transition"
  >
    Click Here
  </button>
  
  <!-- ✅ Signature sign (responsive text) -->
  <div class="mt-10 text-center">
    <p class="text-lg text-gray-700">
      Made by 
      <a 
        href="https://github.com/fatintawsifhoque" 
        target="_blank" 
        class="text-amber-800 font-bold hover:underline"
      >
        Fatin Tawsif Hoque
      </a>
    </p>
  </div>
 </section>
</template>

<script setup>
import { ref } from 'vue';

const container = ['HEADS', 'TAILS']
const output = ref(container[0])
const r = ref(false)

const select = () => {
  let ran = Math.floor(Math.random() * 2)
  output.value = container[ran]
  r.value = true
}
</script>

<style scoped>
</style>