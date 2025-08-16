<template>
  <div v-if="mouse_Enetr" ref="dot" class="w-28 h-28 absolute flex justify-center items-center z-10 rounded-full bg-red-400">
    <span class="text-white font-semibold font-sans tracking-tighter">{{ text }}</span>
  </div>
  
</template>
<script setup>
import { ref, watch, onUnmounted ,onMounted} from 'vue'
import { gsap } from 'gsap'
const dot = ref(null)
const mouse_Enetr = ref(false)
const props = defineProps({
  target: {
    type: Object,
    required: true
  },
  text: {
    type: String,
    default: 'BUY NOW'
  }
})

const updateMouse = (e) => {
    const rect = props.target.getBoundingClientRect() 
  gsap.to(dot.value, {
    x: e.x-rect.left,
    y:e.y - rect.top,
    duration: 0.5,
  })
}


onMounted(() => {
  if (props.target) {
    props.target.addEventListener('mousemove', updateMouse)
    props.target.addEventListener('mouseleave', () => {
      gsap.to(dot.value, {
       scale: 0,
        duration: 0.2,
      })
    })
    props.target.addEventListener('mouseenter', () => {
      mouse_Enetr.value = true
      gsap.to(dot.value, {
        scale: 1,
        duration: 0.2,
      })
    })
  }
})
onUnmounted(() => {
  if (props.target) {
    props.target.removeEventListener('mousemove', updateMouse)
  }
})
</script>
