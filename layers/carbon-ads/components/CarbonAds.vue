<template>
  <div
    ref="container"
    class="carbon min-h-[154px]"
  />
</template>

<script setup lang="ts">
const { id, placement } = useRuntimeConfig().public.carbonAds;

const isInitialized = ref(false);
const container = ref<HTMLElement>();

function init(): void {
  if (!isInitialized.value) {
    isInitialized.value = true;
    const s = document.createElement('script');
    s.id = '_carbonads_js';
    s.src = `//cdn.carbonads.com/carbon.js?serve=${id}&placement=${placement}&format=cover`;
    s.async = true;
    if (container.value !== undefined) {
      container.value.appendChild(s);
    }
  }
}

watch(useRoute(), () => {
  window?._carbonads?.refresh();
});

onMounted(() => {
  init();
});
</script>
