<script>
import TheWelcome from "@/components/TheWelcome.vue";
import MarginPage from "@/components/MarginPage.vue";
import VueEasyLightbox from "vue-easy-lightbox";
import { ref, defineComponent } from "vue";

export default {
  components: {
    VueEasyLightbox,
    MarginPage,
  },
  props: {
    imgList: Array,
    caption: String
  },
  setup(props) {
    const visibleRef = ref(false);
    const indexRef = ref(0); // default 0
    const imgsRef = ref([]);
    // Img Url , string or Array of string
    // ImgObj { src: '', title: '', alt: '' }
    // 'src' is required
    // allow mixing
    
    const onShow = () => {
      visibleRef.value = true;
    };
    const showSingle = () => {
      imgsRef.value =
        "https://4.img-dpreview.com/files/p/E~TS590x0~articles/3925134721/0266554465.jpeg";
      // or
      // imgsRef.value  = {
      //   title: 'this is a placeholder',
      //   src: 'http://via.placeholder.com/350x150'
      // }
      onShow();
    };
    const showMultiple = () => {
      imgsRef.value = props.imgList;
      // or
      // imgsRef.value = [
      //   { title: 'test img', src: 'http://via.placeholder.com/350x150' },
      //   'http://via.placeholder.com/350x150'
      // ]
      indexRef.value = 0; // index of imgList
      onShow();
    };
    const onHide = () => (visibleRef.value = false);

    const displayImgRef = ref(props.imgList[0]);

    return {
      displayImgRef,
      visibleRef,
      indexRef,
      imgsRef,
      showMultiple,
      onHide,
    };
  },
};
</script>

<template>
  <div class="img-frame">
    <img @click="showMultiple" :src="displayImgRef" width="200" height="200" />
    <p>
      {{ caption }}
    </p>
    <vue-easy-lightbox
      :visible="visibleRef"
      :imgs="imgsRef"
      :index="indexRef"
      :moveDisabled="true"
      :scrollDisabled="true"
      @hide="onHide"
    ></vue-easy-lightbox>
  </div>
</template>

<style scoped>
img {
  max-width: 100%;
  max-height: 100%;
  border: 6px solid #ffff;
  margin: 3px 10px 6px;
}

div.img-frame{
  text-align: center;
}
</style>