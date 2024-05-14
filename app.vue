<template>
  <div>
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>

<script setup>
const { setLocale, locale } = useI18n();
onMounted(() => {
  setLocale("fa");
});
</script>
