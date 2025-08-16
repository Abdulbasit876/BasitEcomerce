<template>
  <div>
    <button
      :class="`font-[600] px-6 py-3 ${border&&'border'} rounded transition duration-300`"
      :style="{
        backgroundColor: bg,
        color: color,
        '--hover-bg': hover_bg,
        '--hover-text': hover_text
      }"
    >
      <slot></slot>
    </button>
  </div>
</template>

<script setup>
const props = defineProps({
  hover_bg: { type: String, default: 'white' },
  hover_text: { type: String, default: 'black' },
  bg: { type: String, default: 'white' },
  color: { type: String, default: 'black' },
    border: { type: Boolean, default: false }
})
</script>

<style scoped>
button:hover {
  background-color: var(--hover-bg) !important;
  color: var(--hover-text) !important;
}
</style>
