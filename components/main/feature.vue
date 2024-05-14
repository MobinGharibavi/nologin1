<template>
  <div
    class="max-w-7xl my-20 w-full bg-white mx-auto shadow border rounded-xl grid lg:grid-cols-3 lg:grid-rows-2 divide-y divide-x rtl:divide-x-reverse"
  >
    <div
      v-for="(item, index) in items"
      :key="index"
      class="flex gap-2 justify-center py-8 items-center flex-col text-center"
    >
      <main
        class="rounded-full w-max p-2 bg-blue-100 text-blue-500 flex items-center justify-center"
      >
        <icon :name="item.icon" size="2.5rem" />
      </main>
      <h6 class="font-semibold">{{ item.title }}</h6>
      <p class="text-gray-600 w-3/4">{{ item.description }}</p>
    </div>
  </div>
</template>

<script setup>
const { t } = useI18n();

const items = ref([
  {
    icon: "iconoir:percentage-circle-solid",
    title: t("main.feature.best_price.title"),
    description: t("main.feature.best_price.description"),
  },
  {
    icon: "streamline:customer-support-1-solid",
    title: t("main.feature.support.title"),
    description: t("main.feature.support.description"),
  },
  {
    icon: "ph:cpu-bold",
    title: t("main.feature.cpu.title"),
    description: t("main.feature.cpu.description"),
  },
  {
    icon: "bxs:happy-alt",
    title: t("main.feature.ux.title"),
    description: t("main.feature.ux.description"),
  },
  {
    icon: "bxs:bookmark-alt-minus",
    title: t("main.feature.services.title"),
    description: t("main.feature.services.description"),
  },
  {
    icon: "solar:card-bold",
    title: t("main.feature.payment.title"),
    description: t("main.feature.payment.description"),
  },
]);
</script>
