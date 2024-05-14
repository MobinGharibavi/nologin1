<template>
  <section class="flex items-center justify-center flex-col w-full gap-5">
    <h5 class="font-bold text-3xl">در این تاریخ پروازی وجود ندارد</h5>
    <p class="text-gray-500">نزدیک ترین پرواز های موجود را مشاهده میکنید.</p>

    <div class="grid grid-cols-5 grid-rows-5 gap-1">
      <div
        v-for="(item, index) in date"
        :key="index"
        class="flex px-5 py-2 rounded-xl flex-col items-center justify-center border-2 bg-white"
      >
        <span>{{ item.day }}-{{ item.date }}</span>
        <p class="text-red-400">1.200$</p>
      </div>
    </div>

    <div class="flex items-center gap-3">
      <button class="btn-primary flex items-center">
        <Icon name="mingcute:right-line" />
        <span>25 روز قبل</span>
      </button>
      <button class="btn-primary flex items-center">
        <span>25 روز بعد</span>
        <Icon name="mingcute:left-line" />
      </button>
    </div>
  </section>
</template>

<script setup>
import { addDay, format } from "@formkit/tempo";
const route = useRoute();
const { locale } = useI18n();
const date = ref([]);

for (let i = 0; i < 25; i++) {
  const tt = format(addDay("2013-03-15", i), "dddd", locale.value);
  const dd = format(addDay("2013-03-15", i), "MM/DD", locale.value);
  date.value.push({
    day: tt,
    date: dd,
  });
}
</script>
