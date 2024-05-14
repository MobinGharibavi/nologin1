<template>
  <div class="max-w-7xl w-full mx-auto space-y-6">
    <h1 class="text-2xl font-bold block">
      {{ $t("main.about_travel.title") }}
    </h1>

    <div class="flex flex-col gap-2.5">
      <h4 class="text-lg font-bold">
        {{ $t("main.about_travel.second_title") }}
      </h4>
      <p class="text-gray-500 lg:w-3/4">
        {{ $t("main.about_travel.description") }}
      </p>
    </div>
  </div>
</template>
