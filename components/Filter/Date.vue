<template>
  <div class="w-[1000px] mt-52 lg:mt-0">
    <Carousel dir="rtl" :breakpoints="breakpoints">
      <Slide v-for="(item, index) in date" :key="index">
        <label
          class="select flex-col bg-white rounded-lg text-center border border-transparent transition-all hover:bg-[#E4F0FF] hover:border-[#0A77FF] hover:text-[#0A77FF] w-[129px] h-14 cursor-pointer text-sm text-[#1D1B20] flex items-center justify-center"
          :class="{
            '!text-[#0A77FF] !border-[#0A77FF] !bg-[#E4F0FF]': item === openTab,
          }"
        >
          <input
            type="radio"
            v-model="openTab"
            :value="item"
            :checked="item === openTab"
            class="hidden"
          />
          <span class="text">{{ item.date }}</span>
          <span class="font-semibold">{{ item.day }}</span>
        </label>
      </Slide>
    </Carousel>
  </div>
</template>

<script setup>
const { date } = defineProps({
  date: [Object],
});
const breakpoints = ref({
  // 700px and up
  0: {
    itemsToShow: 7,
  },
  700: {
    itemsToShow: 7,
  },
  // 1024 and up
  1024: {
    itemsToShow: 7,
  },
});
const openTab = ref(new Date());

</script>
