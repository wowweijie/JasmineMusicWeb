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
      <gallery>
        <ImageBox
          :imgList="[
            'https://4.img-dpreview.com/files/p/E~TS590x0~articles/3925134721/0266554465.jpeg',
            'https://drive.google.com/uc?id=193y4-7w53sQovSd8lPT850VcU6xABV6m',
          ]"
          caption="HIHIH"
        />
        <ImageBox
          :imgList="[
            'https://4.img-dpreview.com/files/p/E~TS590x0~articles/3925134721/0266554465.jpeg',
            'https://drive.google.com/uc?id=193y4-7w53sQovSd8lPT850VcU6xABV6m',
          ]"
          caption="HIHIH"
        />
        <ImageBox
          :imgList="[
            'https://4.img-dpreview.com/files/p/E~TS590x0~articles/3925134721/0266554465.jpeg',
            'https://drive.google.com/uc?id=193y4-7w53sQovSd8lPT850VcU6xABV6m',
          ]"
          caption="HIHIH"
        />
        <ImageBox
          :imgList="[
            'https://4.img-dpreview.com/files/p/E~TS590x0~articles/3925134721/0266554465.jpeg',
            'https://drive.google.com/uc?id=193y4-7w53sQovSd8lPT850VcU6xABV6m',
          ]"
          caption="HIHIH"
        />
      </gallery>
      <br />
      <br />
    </MarginPage>
  </main>
</template>

<style scoped>
gallery {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  row-gap: 30px;
}
</style>