<template>
  <FilterBooking />
  <section class="max-w-7xl relative w-full mx-auto mb-20 mt-40">
    <div class="flex gap-5">
      <UtilsFilter />

      <!-- <FilterNotFound /> -->
      <div class="flex flex-col w-full gap-5">
        <FilterDate :date />
        <FilterRecomend />
        <div class="flex flex-col w-full gap-5">
          <div class="p-1 hidden lg:inline bg-pink-600 rounded-xl">
            <h5 class="text-white p-3 text-2xl font-semibold">پیشنهاد ویژه</h5>
            <main
              class="bg-white rounded-xl flex flex-col w-full h-max px-5 py-3 shadow gap-7"
            >
              <div class="flex items-center justify-between">
                <div
                  class="flex items-center gap-3 divide-x-2 rtl:divide-x-reverse"
                >
                  <span class="text-orange-500">پیشنهاد ویژه</span>
                  <span class="pr-3">سیستمی</span>
                </div>
                <div class="flex items-center gap-5">
                  <span class="text-pink-500">6 صندلی باقی مانده</span>
                  <div class="flex items-end gap-1">
                    <Icon name="mingcute:down-line" size="1rem" />
                    <span>قوانین پرواز</span>
                  </div>
                  <div class="flex items-end gap-1">
                    <Icon name="mingcute:down-line" size="1rem" />
                    <span>جزئیات پرواز</span>
                  </div>
                </div>
              </div>

              <div class="flex items-center justify-between">
                <div class="flex flex-col">
                  <div>
                    <div class="flex items-center justify-center">
                      <div
                        class="w-10 h-10 rounded-full border-2 border-white bg-[#D9D9D9] -mr-5 rtl:mr-0"
                      ></div>
                      <div
                        class="w-10 h-10 rounded-full border-2 border-white bg-[#D9D9D9] rtl:-mr-5"
                      ></div>
                    </div>
                    <p class="text-xs text-[#938F96]">THR , MHD</p>
                  </div>
                </div>

                <div class="flex items-center gap-5">
                  <div>
                    <div>
                      <p
                        class="font-bold flex gap-2 rtl:justify-end rtl:flex-row-reverse"
                      >
                        08:25 <span class="text-gray-500">PM</span>
                      </p>
                      <p class="text-[#7D8590]">IMK Mon Apr 01 2024</p>
                    </div>
                  </div>
                  <div class="flex flex-col justify-center items-center">
                    <Icon
                      name="fluent:airplane-24-filled"
                      class="rtl:rotate-180"
                      color="gray"
                    />
                    <p class="text-center text-xs text-[#605D64]">بدون توقف</p>
                    <p class="text-center text-xs text-[#605D64]">MHD</p>
                  </div>
                  <div>
                    <div>
                      <p
                        class="font-bold flex gap-2 rtl:justify-end rtl:flex-row-reverse"
                      >
                        08:25 <span class="text-gray-500">PM</span>
                      </p>
                      <p class="text-[#7D8590]">IMK Mon Apr 01 2024</p>
                    </div>
                  </div>
                </div>

                <div class="flex flex-col gap-2">
                  <div class="flex items-center gap-2">
                    <p class="font-bold text-lg text-gray-400">تومان</p>
                    <span class="text-blue-500 font-bold">16,200,000</span>
                  </div>

                  <button class="btn-outline">انتخاب پرواز</button>
                </div>
              </div>
            </main>
          </div>
          <div class="p-1 lg:hidden bg-pink-600 rounded-xl">
            <h5 class="text-white p-3 text-2xl font-semibold">پیشنهاد ویژه</h5>
            <main
              class="bg-white rounded-xl flex flex-col w-full h-max px-5 py-3 shadow gap-7"
            >
              <div class="flex items-center justify-between">
                <div
                  class="flex items-center gap-3 divide-x-2 rtl:divide-x-reverse"
                >
                  <span class="text-orange-500">پیشنهاد ویژه</span>
                  <span class="pr-3">سیستمی</span>
                </div>

                <div class="flex">
                  <div class="flex items-center flex-row-reverse gap-1">
                    <div class="flex items-center justify-center">
                      <div
                        class="w-10 h-10 rounded-full border-2 border-white bg-[#D9D9D9] -mr-5 rtl:mr-0"
                      ></div>
                      <div
                        class="w-10 h-10 rounded-full border-2 border-white bg-[#D9D9D9] rtl:-mr-5"
                      ></div>
                    </div>
                    <p class="text-xs text-[#938F96]">THR , MHD</p>
                  </div>
                </div>
              </div>

              <div class="flex flex-col items-center justify-between">
                <div class="flex items-center gap-5">
                  <div>
                    <div>
                      <p
                        class="font-bold flex gap-2 rtl:justify-end rtl:flex-row-reverse"
                      >
                        08:25 <span class="text-gray-500">PM</span>
                      </p>
                      <p class="text-[#7D8590]">IMK Mon Apr 01 2024</p>
                    </div>
                  </div>
                  <div class="flex flex-col justify-center items-center">
                    <Icon
                      name="fluent:airplane-24-filled"
                      class="rtl:rotate-180"
                      color="gray"
                    />
                    <p class="text-center text-xs text-[#605D64]">بدون توقف</p>
                    <p class="text-center text-xs text-[#605D64]">MHD</p>
                  </div>
                  <div>
                    <div>
                      <p
                        class="font-bold flex gap-2 rtl:justify-end rtl:flex-row-reverse"
                      >
                        08:25 <span class="text-gray-500">PM</span>
                      </p>
                      <p class="text-[#7D8590]">IMK Mon Apr 01 2024</p>
                    </div>
                  </div>
                </div>

                <div class="flex justify-between w-full">
                  <span class="text-pink-500">6 صندلی باقی مانده</span>
                  <div class="flex items-center gap-2">
                    <p class="font-bold text-lg text-gray-400">تومان</p>
                    <span class="text-blue-500 font-bold">16,200,000</span>
                  </div>
                </div>
              </div>
            </main>
          </div>
          <UtilsTicket v-for="(item, index) in 3" :key="index" />
          <UtilsTicketMobile v-for="(item, index) in 3" :key="index" />
        </div>

        <div class="p-1 flex flex-col gap-5">
          <h5 class="p-3 text-2xl font-semibold">پرواز های تکمیل ظرفیت</h5>
          <main
            v-for="(item, index) in 3"
            :key="index"
            class="bg-white rounded-xl hidden lg:flex flex-col w-full h-max px-5 py-3 shadow gap-7"
          >
            <div class="flex items-center justify-between">
              <div
                class="flex items-center gap-3 divide-x-2 rtl:divide-x-reverse"
              >
                <span class="pr-3">سیستمی</span>
              </div>
              <div class="flex items-center gap-5">
                <div class="flex items-end gap-1">
                  <Icon name="mingcute:down-line" size="1rem" />
                  <span>قوانین پرواز</span>
                </div>
                <div class="flex items-end gap-1">
                  <Icon name="mingcute:down-line" size="1rem" />
                  <span>جزئیات پرواز</span>
                </div>
              </div>
            </div>

            <div class="flex items-center justify-between">
              <div class="flex flex-col">
                <div>
                  <div class="flex items-center justify-center">
                    <div
                      class="w-10 h-10 rounded-full border-2 border-white bg-[#D9D9D9] -mr-5 rtl:mr-0"
                    ></div>
                    <div
                      class="w-10 h-10 rounded-full border-2 border-white bg-[#D9D9D9] rtl:-mr-5"
                    ></div>
                  </div>
                  <p class="text-xs text-[#938F96]">THR , MHD</p>
                </div>
              </div>

              <div class="flex items-center gap-5">
                <div>
                  <div>
                    <p
                      class="font-bold flex gap-2 rtl:justify-end rtl:flex-row-reverse"
                    >
                      08:25 <span class="text-gray-500">PM</span>
                    </p>
                    <p class="text-[#7D8590]">IMK Mon Apr 01 2024</p>
                  </div>
                </div>
                <div class="flex flex-col justify-center items-center">
                  <Icon
                    name="fluent:airplane-24-filled"
                    class="rtl:rotate-180"
                    color="gray"
                  />
                  <p class="text-center text-xs text-[#605D64]">بدون توقف</p>
                </div>
                <div>
                  <div>
                    <p
                      class="font-bold flex gap-2 rtl:justify-end rtl:flex-row-reverse"
                    >
                      08:25 <span class="text-gray-500">PM</span>
                    </p>
                    <p class="text-[#7D8590]">IMK Mon Apr 01 2024</p>
                  </div>
                </div>
              </div>

              <div class="flex flex-col gap-2">
                <div class="flex items-center gap-2">
                  <p class="font-bold text-lg text-gray-400">تومان</p>
                  <span class="font-bold">16,200,000</span>
                </div>

                <button class="btn-outline text-black border-gray-300 border-2">
                  تکمیل ظرفیت
                </button>
              </div>
            </div>
          </main>

          <main
            v-for="(item, index) in 3"
            :key="index"
            class="bg-white rounded-xl lg:hidden flex flex-col w-full h-max px-5 py-3 shadow gap-7"
          >
            <div class="flex items-center justify-between">
              <div
                class="flex items-center gap-3 divide-x-2 rtl:divide-x-reverse"
              >
                <span class="pr-3">سیستمی</span>
              </div>

              <div class="flex">
                <div class="flex items-center flex-row-reverse gap-1">
                  <div class="flex items-center justify-center">
                    <div
                      class="w-10 h-10 rounded-full border-2 border-white bg-[#D9D9D9] -mr-5 rtl:mr-0"
                    ></div>
                    <div
                      class="w-10 h-10 rounded-full border-2 border-white bg-[#D9D9D9] rtl:-mr-5"
                    ></div>
                  </div>
                  <p class="text-xs text-[#938F96]">THR , MHD</p>
                </div>
              </div>
            </div>

            <div class="flex flex-col items-center justify-between">
              <div class="flex items-center gap-5">
                <div>
                  <div>
                    <p
                      class="font-bold flex gap-2 rtl:justify-end rtl:flex-row-reverse"
                    >
                      08:25 <span class="text-gray-500">PM</span>
                    </p>
                    <p class="text-[#7D8590]">IMK Mon Apr 01 2024</p>
                  </div>
                </div>
                <div class="flex flex-col justify-center items-center">
                  <Icon
                    name="fluent:airplane-24-filled"
                    class="rtl:rotate-180"
                    color="gray"
                  />
                  <p class="text-center text-xs text-[#605D64]">بدون توقف</p>
                  <p class="text-center text-xs text-[#605D64]">MHD</p>
                </div>
                <div>
                  <div>
                    <p
                      class="font-bold flex gap-2 rtl:justify-end rtl:flex-row-reverse"
                    >
                      08:25 <span class="text-gray-500">PM</span>
                    </p>
                    <p class="text-[#7D8590]">IMK Mon Apr 01 2024</p>
                  </div>
                </div>
              </div>

              <div class="flex justify-end w-full">
                <div class="flex items-center gap-2">
                  <p class="font-bold text-lg text-gray-400">تومان</p>
                  <span class="font-bold">16,200,000</span>
                </div>
              </div>
            </div>
          </main>
        </div>

        <p class="mx-auto">به انتهای لیست رسیدید</p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { addDay, format } from "@formkit/tempo";
const route = useRoute();
const { locale } = useI18n();
const date = ref([]);

for (let i = 0; i < 20; i++) {
  const tt = format(addDay("2013-03-15", i), "dddd", locale.value);
  const dd = format(addDay("2013-03-15", i), "MM/DD", locale.value);
  date.value.push({
    day: tt,
    date: dd,
  });
}
</script>
