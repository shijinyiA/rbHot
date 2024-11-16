<template>
  <footer>
    <div class="copyright">
      <n-text class="description" v-html="packageJson.description" />
      <n-text
        class="author"
        :depth="3"
        v-html="packageJson.author"
        @click="jumpLink(packageJson.github)"
      />
    </div>
    <n-text
      v-if="icp"
      :depth="3"
      class="icp"
      v-html="icp"
      @click="jumpLink('https://beian.miit.gov.cn/')"
    />
  </footer>
</template>

<script setup>
import packageJson from "@/../package.json";

const icp = ref(import.meta.env.VITE_ICP ? import.meta.env.VITE_ICP : null);

// 链接跳转
const jumpLink = (url) => {
  window.open(url);
};
</script>
