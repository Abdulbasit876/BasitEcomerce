<template>
  <div class=" z-10 relative">
   
   <div ref="target" class="top overflow-hidden border-2 border-red-600 relative  w-full z-10 ">
      <DotFollow v-if="target" :target="target"/>
     <div class="overlay w-full h-full absolute top-0 left-0 z-0 inset-0 bg-[linear-gradient(180deg,#0084D6_-50%,#1a1a1a_100%)] opacity-50 "></div>
        <Navbar class="z-10 relative" />
     <div class= "z-10 relative w-full h-screen font-sans  px-8 text-white flex flex-col items-start justify-center gap-4">
        <h1 class="text-7xl tracking-tighter font-semibold h-24 overflow-hidden "><span :ref="select_text" class="inline-block transform translate-y-[100px]">Raining</span> <span :ref="select_text" class=" inline-block transform translate-y-[100px] ">Offers</span> <span :ref="select_text" class="inline-block transform translate-y-[100px]">For</span></h1>
        <h1 class="text-7xl  tracking-tighter h-24 font-semibold overflow-hidden"> <span :ref="select_text" class="inline-block transform translate-y-[100px]">Hot</span> <span :ref="select_text" class="inline-block transform translate-y-[100px]">Summer!</span></h1>
        <h1 class="font-[500] tracking-tighter mb-10 text-3xl">25% Off On All Products</h1>
       <div class="flex items-center gap-4">
         <Button bg="white" color="black" hover_text="white" hover_bg="black" >
          Shop Now
        </Button>
         <Button bg="none" color="white" hover_text="black" hover_bg="white" border="true" >
          Shop Now
        </Button>
       </div>
      </div>
     </div>
     <main>
      <div class="w-full h-screen bg-slate-700 "></div>
     </main>
   </div>
</template>

<script setup>
import { onMounted, ref } from "vue";
import Button from "../components/Button.vue";
import DotFollow from "../components/dotFollow.vue";
import Navbar from "../components/Navbar.vue";
import { gsap } from "gsap";
const target = ref(null)
const text=ref([])
 const select_text =(e)=>{  if(e && !text.value.includes(e)){
    text.value.push(e)
  }
 }
const tl = gsap.timeline()

const textEffect = () => {
  text.value.forEach((el, index) => {
    tl.to(el, {
      y: 0,           // 50px niche se start
          // fade in effect
      duration: 1,
      ease: "power3.out"
    }, index * 0.2)    // har line me 0.2s ka gap
  })
}

 onMounted(()=>{
  textEffect()
 })
</script>

<style scoped>

.top {
 background-image: url('../assets/main.jpg');
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  width: 100%;   
  height: 100%; 
background-attachment: fixed;
}

</style>
