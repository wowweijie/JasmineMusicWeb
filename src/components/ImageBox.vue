<script>
import TheWelcome from '@/components/TheWelcome.vue'
import MarginPage from '@/components/MarginPage.vue'
import VueEasyLightbox from 'vue-easy-lightbox'
import { ref, defineComponent } from 'vue'

export default {
  components:{
    VueEasyLightbox,
    MarginPage
  },
  props: {
    imgList: Array
  },
  setup(props) {
    const visibleRef = ref(false)
    const indexRef = ref(0) // default 0
    const imgsRef = ref([])
    // Img Url , string or Array of string
    // ImgObj { src: '', title: '', alt: '' }
    // 'src' is required
    // allow mixing

    const onShow = () => {
      visibleRef.value = true
    }
    const showSingle = () => {
      imgsRef.value = "https://4.img-dpreview.com/files/p/E~TS590x0~articles/3925134721/0266554465.jpeg"
      // or
      // imgsRef.value  = {
      //   title: 'this is a placeholder',
      //   src: 'http://via.placeholder.com/350x150'
      // }
      onShow()
    }
    const showMultiple = () => {
      imgsRef.value = props.imgList
      // or
      // imgsRef.value = [
      //   { title: 'test img', src: 'http://via.placeholder.com/350x150' },
      //   'http://via.placeholder.com/350x150'
      // ]
      indexRef.value = 0 // index of imgList
      onShow()
    }
    const onHide = () => (visibleRef.value = false)

    return {
      visibleRef,
      indexRef,
      imgsRef,
      showSingle,
      showMultiple,
      onHide
    }
  }
}
</script>

<template>
    <button @click="showMultiple">Show a group of pictures.</button>

  <vue-easy-lightbox
      :visible="visibleRef"
      :imgs="imgsRef"
      :index="indexRef"
      :moveDisabled=true
      scrollDisabled=true
      @hide="onHide"
    ></vue-easy-lightbox>
</template>