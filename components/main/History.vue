<template>
  <section class="max-w-7xl w-full mx-auto space-y-6 mt-[26rem] lg:mt-44">
    <div class="flex items-center gap-5">
      <div class="flex items-center whitespace-nowrap gap-1">
        <Icon name="ep:refresh-left" />
        <span>{{ $t("main.history.title") }}:</span>
      </div>

      <div class="box-content overflow-auto no-scrollbar flex gap-3 items-center">
        <template v-for="(item, index) in 5" :key="index">
          <main
            class="rounded-full border px-4 py-2 bg-white flex items-end gap-1"
          >
            <span>تهران</span>
            <p class="text-gray-400">به</p>
            <span>مشهد</span>
            <button>
              <Icon name="uim:multiply" />
            </button>
          </main>
        </template>
      </div>
    </div>

    <div class="grid lg:grid-cols-2 gap-5">
      <div class="bg-white hidden lg:inline h-64 rounded-xl"></div>
      <div class="bg-white h-64 rounded-xl"></div>
    </div>
  </section>
</template>
