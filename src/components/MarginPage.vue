<script setup> 
import { reactive } from 'vue'

const props = defineProps({
  margin: {
    type: Number,
    default: 30,
  },
  fontSize: {
    type: Number,
    default: 18,
  },
});

const styleObject = reactive({
    margin: `0 ${props.margin}px`,
    fontSize: `${props.fontSize} px`
})

console.log(styleObject)
</script>
<template>
    <div :style="styleObject">
        <slot></slot>
    </div>
</template>