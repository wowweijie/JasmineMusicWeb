<script setup> 
import { reactive } from 'vue'

const props = defineProps({
  hmargin: {
    type: Number,
    default: 30,
  },
  vmargin: {
    type: Number,
    default: 0,
  },
  fontSize: {
    type: Number,
    default: 18,
  },
});

const styleObject = reactive({
    margin: `${props.hmargin}px ${props.hmargin}px`,
    fontSize: `${props.fontSize} px`
})

console.log(styleObject)
</script>
<template>
    <div :style="styleObject">
        <slot></slot>
    </div>
</template>