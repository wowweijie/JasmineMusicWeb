<script>
import ImageBox from "@/components/ImageBox.vue";
import MarginPage from "@/components/MarginPage.vue";
import { ref, defineComponent } from "vue";

export default {
  components: {
    ImageBox,
    MarginPage,
  },
};
</script>

<template>
  <main>
    <MarginPage>
      <ImageBox
        :imgList="[
          'https://4.img-dpreview.com/files/p/E~TS590x0~articles/3925134721/0266554465.jpeg',
          'https://drive.google.com/uc?id=193y4-7w53sQovSd8lPT850VcU6xABV6m'
        ]"
      />
    </MarginPage>
  </main>
</template>