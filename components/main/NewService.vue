<template>
  <section class="max-w-7xl my-20 w-full mx-auto space-y-6">
    <h1 class="text-2xl font-bold block">خدمات جدید ما</h1>

    <NuxtLink
      :to="`/${locale}`"
      class="flex justify-between bg-white border rounded-xl px-5 py-3 items-center w-full"
    >
      <div class="flex items-center gap-3">
        <main
          class="rounded-full w-max p-2 bg-blue-100 text-blue-500 flex items-center justify-center"
        >
          <icon name="ri:shield-check-fill" size="2.5rem" />
        </main>

        <div class="flex flex-col">
          <h6 class="font-semibold text-lg">
            {{ $t("main.new_service.option_1.title") }}
          </h6>
          <p class="text-gray-500">
            {{ $t("main.new_service.option_1.body") }}
          </p>
        </div>
      </div>
      <Icon name="uim:angle-left" />
    </NuxtLink>

    <div class="flex items-center gap-4 flex-col lg:flex-row">
      <NuxtLink
        :to="`/${locale}`"
        class="flex bg-white justify-between border rounded-xl px-5 py-3 items-center w-full"
      >
        <div class="flex items-center gap-3">
          <main
            class="rounded-full w-max p-2 bg-blue-100 text-blue-500 flex items-center justify-center"
          >
            <icon name="streamline:cards-solid" size="2.5rem" />
          </main>

          <div class="flex flex-col">
            <h6 class="font-semibold text-lg">
              {{ $t("main.new_service.option_2.title") }}
            </h6>
            <p class="text-gray-500">
              {{ $t("main.new_service.option_2.body") }}
            </p>
          </div>
        </div>
        <Icon name="uim:angle-left" />
      </NuxtLink>

      <NuxtLink
        :to="`/${locale}`"
        class="flex bg-white justify-between border rounded-xl px-5 py-3 items-center w-full"
      >
        <div class="flex items-center gap-3">
          <main
            class="rounded-full w-max p-2 bg-blue-100 text-blue-500 flex items-center justify-center"
          >
            <icon name="mage:building-tree-fill" size="2.5rem" />
          </main>

          <div class="flex flex-col">
            <h6 class="font-semibold text-lg">
              {{ $t("main.new_service.option_3.title") }}
            </h6>
            <p class="text-gray-500">
              {{ $t("main.new_service.option_3.body") }}
            </p>
          </div>
        </div>
        <Icon name="uim:angle-left" />
      </NuxtLink>
    </div>
  </section>
</template>

<script setup>
const { locale } = useI18n();
</script>
