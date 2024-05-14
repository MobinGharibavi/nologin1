<template>
  <header class="bg-white z-30 sticky lg:static top-0 border-b">
    <div class="max-w-7xl w-fll mx-auto">
      <div
        class="flex justify-between items-center lg:container px-5 lg:px-0 mx-auto py-4 lg:py-6"
      >
        <div class="flex gap-10 items-center">
          <NuxtLink :to="`/${locale}`"
            ><img alt="logo" src="/img/Black-orange 1.png"
          /></NuxtLink>

          <div class="lg:flex hidden gap-10 items-center">
            <main
              v-click-outside="clickshowService"
              @click="showService = !showService"
              class="flex cursor-pointer relative items-end"
            >
              <span>{{ $t("navBar.service.title") }}</span>
              <Icon name="mingcute:down-line" size="1rem" />

              <div class="absolute">
                <TransitionExpand :duration="500">
                  <div
                    class="flex flex-col w-72 gap-5 py-5 z-50 h-max -right-5 top-5 px-5 absolute bg-white rounded-lg shadow"
                    v-if="showService"
                  >
                    <div class="flex flex-col">
                      <div class="flex items-center gap-2">
                        <Icon name="icons8:airport" size="2rem" />
                        <span class="text-xl">هواپیما</span>
                      </div>
                      <p class="text-gray-500">
                        آسان ترین راه برای رزرو بلیط هواپیما.
                      </p>
                    </div>
                    <div class="flex flex-col">
                      <div class="flex items-center gap-2">
                        <Icon name="ri:hotel-line" size="2rem" />
                        <span class="text-xl">هتل</span>
                      </div>
                      <p class="text-gray-500">
                        رزرو اقامتگاه در همه جای ایران.
                      </p>
                    </div>
                    <div class="flex flex-col">
                      <div class="flex items-center gap-2">
                        <Icon name="streamline:cards" size="2rem" />
                        <span class="text-xl">ویزا</span>
                      </div>
                      <p class="text-gray-500">درخواست ویزا مسافرتی به آسانی</p>
                    </div>
                    <div class="flex flex-col">
                      <div class="flex items-center gap-2">
                        <Icon name="iconamoon:shield-yes-light" size="2rem" />
                        <span class="text-xl">بیمه</span>
                      </div>
                      <p class="text-gray-500">
                        با بیمه مسافرتی سفری ایمن و مطمئن را تجربه کنید.
                      </p>
                    </div>
                  </div>
                </TransitionExpand>
              </div>
            </main>
            <span>{{ $t("navBar.support") }}</span>
            <span>{{ $t("navBar.contact") }}</span>
            <span>{{ $t("navBar.about") }}</span>
          </div>
        </div>
        <div class="lg:flex hidden items-center gap-5">
          <div class="flex relative items-center gap-4 ml-auto">
            <div
              v-if="locale == 'en'"
              @click="showLang = !showLang"
              v-click-outside="clickShowLang"
              class="flex relative items-center gap-3 cursor-pointer"
            >
              <svg
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M13.2333 7.7418L9.99998 10.9751L6.76665 7.7418C6.44165 7.4168 5.91665 7.4168 5.59165 7.7418C5.26665 8.0668 5.26665 8.5918 5.59165 8.9168L9.41665 12.7418C9.74165 13.0668 10.2667 13.0668 10.5917 12.7418L14.4167 8.9168C14.7417 8.5918 14.7417 8.0668 14.4167 7.7418C14.0917 7.42513 13.5583 7.4168 13.2333 7.7418Z"
                  fill="#1D1B20"
                />
              </svg>
              <p>{{ $t("navBar.language.en") }}</p>
              <Icon name="emojione:flag-england" />
            </div>
            <div
              v-else-if="locale == 'fa'"
              @click="showLang = !showLang"
              v-click-outside="clickShowLang"
              class="flex relative items-center gap-3 cursor-pointer"
            >
              <svg
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M13.2333 7.7418L9.99998 10.9751L6.76665 7.7418C6.44165 7.4168 5.91665 7.4168 5.59165 7.7418C5.26665 8.0668 5.26665 8.5918 5.59165 8.9168L9.41665 12.7418C9.74165 13.0668 10.2667 13.0668 10.5917 12.7418L14.4167 8.9168C14.7417 8.5918 14.7417 8.0668 14.4167 7.7418C14.0917 7.42513 13.5583 7.4168 13.2333 7.7418Z"
                  fill="#1D1B20"
                />
              </svg>
              <p>{{ $t("navBar.language.fa") }}</p>
              <Icon name="emojione:flag-for-iran" />
            </div>
            <div
              v-else-if="locale == 'ar'"
              @click="showLang = !showLang"
              v-click-outside="clickShowLang"
              class="flex relative items-center gap-3 cursor-pointer"
            >
              <svg
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M13.2333 7.7418L9.99998 10.9751L6.76665 7.7418C6.44165 7.4168 5.91665 7.4168 5.59165 7.7418C5.26665 8.0668 5.26665 8.5918 5.59165 8.9168L9.41665 12.7418C9.74165 13.0668 10.2667 13.0668 10.5917 12.7418L14.4167 8.9168C14.7417 8.5918 14.7417 8.0668 14.4167 7.7418C14.0917 7.42513 13.5583 7.4168 13.2333 7.7418Z"
                  fill="#1D1B20"
                />
              </svg>
              <p>{{ $t("navBar.language.ar") }}</p>
              <Icon name="emojione:flag-for-saudi-arabia" />
            </div>
            <TransitionExpand>
              <div
                v-if="showLang"
                class="flex flex-col gap-5 py-5 z-50 top-10 px-5 justify-center items-center absolute bg-white rounded-lg shadow"
              >
                <div
                  @click="handleLtrProject('en')"
                  class="flex cursor-pointer items-center gap-2"
                >
                  <span>{{ $t("navBar.language.en") }}</span>
                  <Icon name="emojione:flag-england" />
                </div>
                <div
                  @click="handleRtlProject('fa')"
                  class="flex cursor-pointer items-center gap-2"
                >
                  <span>{{ $t("navBar.language.fa") }}</span>
                  <Icon name="emojione:flag-for-iran" />
                </div>
                <div
                  @click="handleRtlProject('ar')"
                  class="flex cursor-pointer items-center gap-2"
                >
                  <span>{{ $t("navBar.language.ar") }}</span>
                  <Icon name="emojione:flag-for-saudi-arabia" />
                </div>
              </div>
            </TransitionExpand>
          </div>
          <p class="border h-6"></p>
          <div
            v-click-outside="clickshowProfile"
            @click="showProfile = !showProfile"
            class="border-2 relative cursor-pointer px-3 py-1 gap-2 rounded-full flex items-center"
          >
            <Icon name="mingcute:down-line" size="1rem" />
            <span>09184720235</span>

            <div class="absolute">
              <TransitionExpand :duration="500">
                <div
                  class="flex flex-col w-60 gap-5 py-5 z-50 h-max -right-5 top-5 px-5 absolute bg-white rounded-lg shadow"
                  v-if="showProfile"
                >
                  <div class="flex border-b pb-2 justify-between">
                    <div class="flex flex-col gap-2">
                      <span class="text-gray-500">کیف پول</span>
                      <div class="flex items-center gap-3">
                        <span>12,000,000</span>
                        <p class="text-gray-500">تومان</p>
                      </div>
                    </div>

                    <button>
                      <Icon name="ic:outline-plus" />
                    </button>
                  </div>

                  <div class="flex cursor-pointer items-center gap-4">
                    <Icon name="fluent:person-24-regular" />
                    <span>اطلاعات حساب کاربری</span>
                  </div>
                  <div class="flex cursor-pointer items-center gap-4">
                    <Icon name="icon-park-outline:transaction" />
                    <span>تراکنش ها</span>
                  </div>
                  <div class="flex cursor-pointer items-center gap-4">
                    <Icon name="f7:tickets" />
                    <span>بلیط ها</span>
                  </div>
                  <div class="flex cursor-pointer items-center gap-4">
                    <Icon name="mage:building-b" />
                    <span>اقامتگاه ها</span>
                  </div>
                  <div class="flex cursor-pointer items-center gap-4">
                    <Icon name="teenyicons:shield-tick-outline" />
                    <span>بیمه ها</span>
                  </div>
                  <div class="flex cursor-pointer items-center gap-4">
                    <Icon name="mingcute:headphone-line" />
                    <span>پشتیبانی</span>
                  </div>
                  <div
                    class="flex cursor-pointer text-red-500 items-center gap-4"
                  >
                    <Icon name="tabler:logout-2" />
                    <span>خروج از حساب</span>
                  </div>
                </div>
              </TransitionExpand>
            </div>
          </div>
        </div>
        <button class="lg:hidden">
          <Icon name="solar:hamburger-menu-linear" size="2rem"/>
        </button>
      </div>
    </div>
  </header>
</template>

<script setup>
const showLang = ref(false);
const clickShowLang = () => {
  if (showLang.value) {
    showLang.value = false;
  }
};
const showProfile = ref(false);
const clickshowProfile = () => {
  if (showProfile.value) {
    showProfile.value = false;
  }
};
const showService = ref(false);
const clickshowService = () => {
  if (showService.value) {
    showService.value = false;
  }
};

const { setLocale, locale } = useI18n();
const handleRtlProject = (lang) => {
  setLocale(lang);
  document.documentElement.setAttribute("dir", "rtl");
  document.documentElement.setAttribute("lang", lang);
};
const handleLtrProject = (lang) => {
  setLocale(lang);
  document.documentElement.setAttribute("dir", "ltr");
  document.documentElement.setAttribute("lang", lang);
};
</script>
