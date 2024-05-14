<template>
  <section class="relative flex justify-center w-full h-max lg:h-96">
    <div class="w-full relative flex justify-center">
      <img src="/img/head.jpg" class="w-full relative object-cover" alt="" />
      <h1 class="text-white absolute right-32 top-56 text-4xl font-bold">
        بلیط هواپیما
      </h1>
      <section
      class="bg-white gap-5 absolute top-1/2 p-5 max-w-6xl w-full mx-auto rounded-xl flex flex-col"
      >
        <div
          class="flex items-center overflow-auto no-scrollbar gap-10 justify-center border-b"
        >
          <button
            @click="step = 1"
            :class="{ 'border-blue-500 border-b text-blue-500': step == 1 }"
            class="flex gap-2 items-center pb-2 w-max"
          >
            <Icon name="ic:twotone-local-airport" />
            <span>هواپیما</span>
          </button>
          <button
            @click="step = 2"
            :class="{ 'border-blue-500 border-b text-blue-500': step == 2 }"
            class="flex items-center gap-2 pb-2 w-max"
          >
            <Icon name="mingcute:hotel-line" />
            <span>هتل</span>
          </button>
          <button
            @click="step = 3"
            :class="{ 'border-blue-500 border-b text-blue-500': step == 3 }"
            class="flex items-center gap-2 pb-2 w-max"
          >
            <Icon name="streamline:cards" />
            <span>ویزا</span>
          </button>
          <button
            @click="step = 4"
            :class="{ 'border-blue-500 border-b text-blue-500': step == 4 }"
            class="flex items-center gap-2 pb-2 w-max"
          >
            <Icon name="teenyicons:shield-tick-outline" />
            <span>بیمه</span>
          </button>
        </div>

        <div v-if="step == 1" class="flex flex-col gap-5">
          <div class="flex gap-6">
            <div
              v-click-outside="clickOutWay"
              class="flex cursor-pointer relative items-center gap-2"
            >
              <div @click="way = !way">
                <span>یک طرفه</span>
                <icon name="icon-park-outline:down" />
              </div>

              <div
                class="absolute bottom-0 left-0 z-50 h-max w-full bg-white shadow-xl rounded-lg px-4"
              >
                <TransitionExpand :duration="500">
                  <div
                    v-if="way"
                    class="flex flex-col gap-2 rounded-lg px-5 w-[15rem] z-50 bg-white shadow absolute right-0 top-0"
                  >
                    <span class="border-b py-2">یک طرفه</span>
                    <span class="border-b py-2">رفت و برگشت</span>
                    <span class="border-b py-2">چند مسیره</span>

                    <div class="flex items-center gap-2">
                      <button class="btn-outline w-full">انصراف</button>
                      <button class="btn-primary w-full">تایید</button>
                    </div>
                  </div>
                </TransitionExpand>
              </div>
            </div>
            <div
              @click="financial = !financial"
              v-click-outside="clickOutfinancial"
              class="flex cursor-pointer relative items-center gap-2"
            >
              <span>اقتصادی</span>
              <icon name="icon-park-outline:down" />

              <div
                class="absolute bottom-0 left-0 z-50 h-max w-full bg-white shadow-xl rounded-lg px-4"
              >
                <TransitionExpand :duration="500">
                  <div
                    v-if="financial"
                    class="flex flex-col rounded-lg px-5 w-[15rem] z-50 bg-white shadow absolute right-0 top-0"
                  >
                    <span class="border-b py-2">اقتصادی</span>
                    <span class="border-b py-2">پریمیوم</span>
                  </div>
                </TransitionExpand>
              </div>
            </div>
          </div>

          <div class="flex flex-col lg:flex-row gap-2">
            <div
              class="justify-center flex flex-col gap-5 lg:gap-0 lg:flex-row relative"
            >
              <input
                type="text"
                placeholder="مبدا"
                class="border border-[#DCDFE4] px-6 py-[10px] rounded-2xl outline-blue-300"
              />

              <button type="button" class="h-full">
                <Icon
                  name="humbleicons:exchange-horizontal"
                  class="w-[50px] rotate-90 lg:rotate-0 h-[50px] rounded-[50%] absolute bg-white border-2 left-5 lg:-translate-x-1/2 lg:left-1/2 -translate-y-1/2 top-1/2 p-3 flex justify-center items-center"
                />

                <input
                  class="border h-full border-[#DCDFE4] w-full px-5 lg:placeholder:px-3 py-[10px] rounded-2xl outline-blue-300"
                  type="text"
                  placeholder="مقصد"
                />
              </button>
            </div>
            <div
              v-click-outside="clickOutdateAir"
              class="rounded-[16px] relative flex-grow border border-[#DCDFE4] px-6 py-[10px] cursor-pointer"
            >
              <div @click="dateAir = !dateAir">
                <p class="text-sm text-[#938F96]">تاریخ رفت - برگشت</p>
                <p class="font-bold">25 فروردین - 14 اردیبهشت</p>
              </div>
              <div
                class="absolute bottom-0 right-0 top-16 z-50 h-max w-max bg-white shadow-xl rounded-lg px-4"
              >
                <TransitionExpand :duration="500">
                  <div v-if="dateAir" class="flex flex-col">
                    <div
                      class="flex flex-col gap-3 lg:flex-row justify-between border-b py-3 items-center"
                    >
                      <h6 class="text-xl font-bold">تاریخ رفت</h6>
                      <div class="flex items-center gap-3">
                        <span class="text-blue-500 font-semibold cursor-pointer"
                          >برو به امروز</span
                        >
                        <div class="flex items-center gap-2">
                          <div class="checkbox-wrapper-34">
                            <input
                              class="tgl tgl-ios"
                              id="toggle-34"
                              type="checkbox"
                            />
                            <label class="tgl-btn" for="toggle-34"></label>
                          </div>
                          <p class="text-gray-600">تاریخ برگشت</p>
                        </div>
                      </div>
                    </div>
                    <div class="m-2 border-b">
                      <ClientOnly>
                        <VDatePicker
                          locale="fa"
                          v-model.range="range"
                          :columns="columns"
                          :expanded="expanded"
                        />
                      </ClientOnly>
                    </div>
                    <div
                      class="flex flex-col lg:flex-row justify-between mb-2 items-center"
                    >
                      <div
                        class="flex items-center bg-gray-100 gap-5 px-1 py-1 rounded-lg"
                      >
                        <button class="text-gray-700">میلادی</button>
                        <button class="text-blue-500 bg-white p-2 rounded-lg">
                          شمسی
                        </button>
                      </div>

                      <div class="flex items-center gap-2 p-2.5">
                        <button
                          @click="cancelAndResetCalender"
                          class="btn-outline px-8 py-3"
                        >
                          انصراف
                        </button>
                        <button
                          @click="firstDate = !firstDate"
                          class="btn-primary px-8 py-3"
                        >
                          تایید
                        </button>
                      </div>
                    </div>
                  </div>
                </TransitionExpand>
              </div>
            </div>
            <div
              v-click-outside="clickOutPassengerAir"
              class="rounded-[16px] relative border flex-grow border-[#DCDFE4] px-6 py-[10px] cursor-pointer"
            >
              <div @click="PassengerAir = !PassengerAir">
                <p class="text-sm text-[#938F96]">مسافران</p>
                <p class="font-bold">2 بزرگسال - 1 کودک</p>
              </div>
              <div
                class="absolute bottom-0 left-0 top-16 z-50 h-max w-full bg-white shadow-xl rounded-lg px-4"
              >
                <TransitionExpand :duration="500">
                  <div
                    v-if="PassengerAir"
                    class="flex flex-col rounded-lg z-50 bg-white shadow w-full absolute right-0 top-0"
                  >
                    <div
                      class="flex items-center border-b p-2.5 justify-between"
                    >
                      <span class="font-semibold">بزگسال</span>
                      <div class="flex items-center gap-2">
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 24 24"
                          >
                            <path
                              fill="currentColor"
                              d="M19 12.998h-6v6h-2v-6H5v-2h6v-6h2v6h6z"
                            />
                          </svg>
                        </button>

                        <span>0</span>
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500 opacity-50"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 256 256"
                          >
                            <path
                              fill="currentColor"
                              d="M224 128a8 8 0 0 1-8 8H40a8 8 0 0 1 0-16h176a8 8 0 0 1 8 8"
                            />
                          </svg>
                        </button>
                      </div>
                    </div>
                    <div
                      class="flex items-center border-b p-2.5 justify-between"
                    >
                      <span class="font-semibold">کودک</span>
                      <div class="flex items-center gap-2">
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 24 24"
                          >
                            <path
                              fill="currentColor"
                              d="M19 12.998h-6v6h-2v-6H5v-2h6v-6h2v6h6z"
                            />
                          </svg>
                        </button>
                        <span>0</span>

                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500 opacity-50"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 256 256"
                          >
                            <path
                              fill="currentColor"
                              d="M224 128a8 8 0 0 1-8 8H40a8 8 0 0 1 0-16h176a8 8 0 0 1 8 8"
                            />
                          </svg>
                        </button>
                      </div>
                    </div>
                    <div
                      class="flex items-center border-b p-2.5 justify-between"
                    >
                      <span class="font-semibold">نوزاد</span>
                      <div class="flex items-center gap-2">
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 24 24"
                          >
                            <path
                              fill="currentColor"
                              d="M19 12.998h-6v6h-2v-6H5v-2h6v-6h2v6h6z"
                            />
                          </svg>
                        </button>
                        <span>0</span>
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500 opacity-50"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 256 256"
                          >
                            <path
                              fill="currentColor"
                              d="M224 128a8 8 0 0 1-8 8H40a8 8 0 0 1 0-16h176a8 8 0 0 1 8 8"
                            />
                          </svg>
                        </button>
                      </div>
                    </div>
                    <div class="flex items-center gap-2 p-2.5">
                      <button
                        @click="PassengerAir = false"
                        class="rounded-lg w-full flex items-center justify-center px-2.5 py-2 text-white bg-blue-500"
                      >
                        تایید
                      </button>
                      <button
                        @click="PassengerAir = false"
                        class="rounded-lg w-full flex items-center justify-center px-2.5 py-2 text-blue-500 border-2 border-blue-500"
                      >
                        انصراف
                      </button>
                    </div>
                  </div>
                </TransitionExpand>
              </div>
            </div>

            <button class="btn-primary px-10">جستجو</button>
          </div>
        </div>
        <div v-if="step == 2" class="flex flex-col gap-5">
          <div class="flex flex-col lg:flex-row gap-2">
            <div
              v-click-outside="clickOutdestinationHotel"
              class="rounded-[16px] relative border flex-grow border-[#DCDFE4] px-6 py-[10px] cursor-pointer"
            >
              <div @click="destinationHotel = !destinationHotel">
                <p class="text-sm text-[#938F96]">مقصد یا هتل</p>
                <p class="font-bold">تهران</p>
              </div>
              <div
                class="absolute bottom-0 right-0 top-16 z-50 h-max w-full bg-white shadow-xl rounded-lg px-4"
              >
                <TransitionExpand :duration="500">
                  <div
                    v-if="destinationHotel"
                    class="flex flex-col rounded-lg px-5 w-full z-50 bg-white shadow absolute right-0 top-0"
                  >
                    <span
                      v-for="(item, index) in 6"
                      :key="index"
                      class="border-b py-2"
                      >دبی</span
                    >
                  </div>
                </TransitionExpand>
              </div>
            </div>
            <div class="flex flex-grow items-center">
              <div
                @click="dateHotelOrigin = !dateHotelOrigin"
                v-click-outside="clickOutdateHotelOrigin"
                class="rounded-r-[16px] flex-grow relative border border-[#DCDFE4] px-6 py-[10px] cursor-pointer"
              >
                <p class="text-sm text-[#938F96]">تاریخ ورود</p>
                <p class="font-bold">14 فروردین</p>
                <div
                  class="absolute bottom-0 right-0 top-16 z-50 h-max w-max bg-white shadow-xl rounded-lg px-4"
                >
                  <TransitionExpand :duration="500">
                    <div v-if="dateHotelOrigin" class="flex flex-col">
                      <div
                        class="flex flex-col gap-3 lg:flex-row justify-between border-b py-3 items-center"
                      >
                        <h6 class="text-xl font-bold">تاریخ رفت</h6>
                        <div class="flex items-center gap-3">
                          <span
                            class="text-blue-500 font-semibold cursor-pointer"
                            >برو به امروز</span
                          >
                          <div class="flex items-center gap-2">
                            <div class="checkbox-wrapper-34">
                              <input
                                class="tgl tgl-ios"
                                id="toggle-34"
                                type="checkbox"
                              />
                              <label class="tgl-btn" for="toggle-34"></label>
                            </div>
                            <p class="text-gray-600">تاریخ برگشت</p>
                          </div>
                        </div>
                      </div>
                      <div class="m-2 border-b">
                        <ClientOnly>
                          <VDatePicker
                            v-model.range="range"
                            :columns="columns"
                            :expanded="expanded"
                          />
                        </ClientOnly>
                      </div>
                      <div
                        class="flex flex-col lg:flex-row justify-between mb-2 items-center"
                      >
                        <div
                          class="flex items-center bg-gray-100 gap-5 px-1 py-1 rounded-lg"
                        >
                          <button class="text-gray-700">میلادی</button>
                          <button class="text-blue-500 bg-white p-2 rounded-lg">
                            شمسی
                          </button>
                        </div>

                        <div class="flex items-center gap-2 p-2.5">
                          <button
                            @click="cancelAndResetCalender"
                            class="btn-outline px-8 py-3"
                          >
                            انصراف
                          </button>
                          <button
                            @click="firstDate = !firstDate"
                            class="btn-primary px-8 py-3"
                          >
                            تایید
                          </button>
                        </div>
                      </div>
                    </div>
                  </TransitionExpand>
                </div>
              </div>
              <div
                @click="dateHotelDest = !dateHotelDest"
                v-click-outside="clickOutdateHotelDest"
                class="rounded-l-[16px] flex-grow relative border border-[#DCDFE4] px-6 py-[10px] cursor-pointer"
              >
                <p class="text-sm text-[#938F96]">تاریخ خروج</p>
                <p class="font-bold">14 اردیبهشت</p>
                <div
                  class="absolute bottom-0 right-0 top-16 z-50 h-max w-max bg-white shadow-xl rounded-lg px-4"
                >
                  <TransitionExpand :duration="500">
                    <div v-if="dateHotelDest" class="flex flex-col">
                      <div
                        class="flex flex-col gap-3 lg:flex-row justify-between border-b py-3 items-center"
                      >
                        <h6 class="text-xl font-bold">تاریخ رفت</h6>
                        <div class="flex items-center gap-3">
                          <span
                            class="text-blue-500 font-semibold cursor-pointer"
                            >برو به امروز</span
                          >
                          <div class="flex items-center gap-2">
                            <div class="checkbox-wrapper-34">
                              <input
                                class="tgl tgl-ios"
                                id="toggle-34"
                                type="checkbox"
                              />
                              <label class="tgl-btn" for="toggle-34"></label>
                            </div>
                            <p class="text-gray-600">تاریخ برگشت</p>
                          </div>
                        </div>
                      </div>
                      <div class="m-2 border-b">
                        <ClientOnly>
                          <VDatePicker
                            v-model.range="range"
                            :columns="columns"
                            :expanded="expanded"
                          />
                        </ClientOnly>
                      </div>
                      <div
                        class="flex flex-col lg:flex-row justify-between mb-2 items-center"
                      >
                        <div
                          class="flex items-center bg-gray-100 gap-5 px-1 py-1 rounded-lg"
                        >
                          <button class="text-gray-700">میلادی</button>
                          <button class="text-blue-500 bg-white p-2 rounded-lg">
                            شمسی
                          </button>
                        </div>

                        <div class="flex items-center gap-2 p-2.5">
                          <button
                            @click="cancelAndResetCalender"
                            class="btn-outline px-8 py-3"
                          >
                            انصراف
                          </button>
                          <button
                            @click="firstDate = !firstDate"
                            class="btn-primary px-8 py-3"
                          >
                            تایید
                          </button>
                        </div>
                      </div>
                    </div>
                  </TransitionExpand>
                </div>
              </div>
            </div>
            <div
              v-click-outside="clickOutPassengerHotel"
              class="rounded-[16px] flex-grow relative border border-[#DCDFE4] px-6 py-[10px] cursor-pointer"
            >
              <div @click="PassengerHotel = !PassengerHotel">
                <p class="text-sm text-[#938F96]">مسافران</p>
                <p class="font-bold">2 بزرگسال - 1 کودک</p>
              </div>
              <div
                class="absolute bottom-0 left-0 top-16 z-50 h-max w-full bg-white shadow-xl rounded-lg px-4"
              >
                <TransitionExpand :duration="500">
                  <div
                    v-if="PassengerHotel"
                    class="flex flex-col rounded-lg z-50 bg-white shadow w-full absolute right-0 top-0"
                  >
                    <div
                      class="flex items-center border-b p-2.5 justify-between"
                    >
                      <span class="font-semibold">بزگسال</span>
                      <div class="flex items-center gap-2">
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 24 24"
                          >
                            <path
                              fill="currentColor"
                              d="M19 12.998h-6v6h-2v-6H5v-2h6v-6h2v6h6z"
                            />
                          </svg>
                        </button>

                        <span>0</span>
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500 opacity-50"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 256 256"
                          >
                            <path
                              fill="currentColor"
                              d="M224 128a8 8 0 0 1-8 8H40a8 8 0 0 1 0-16h176a8 8 0 0 1 8 8"
                            />
                          </svg>
                        </button>
                      </div>
                    </div>
                    <div
                      class="flex items-center border-b p-2.5 justify-between"
                    >
                      <span class="font-semibold">کودک</span>
                      <div class="flex items-center gap-2">
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 24 24"
                          >
                            <path
                              fill="currentColor"
                              d="M19 12.998h-6v6h-2v-6H5v-2h6v-6h2v6h6z"
                            />
                          </svg>
                        </button>
                        <span>0</span>

                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500 opacity-50"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 256 256"
                          >
                            <path
                              fill="currentColor"
                              d="M224 128a8 8 0 0 1-8 8H40a8 8 0 0 1 0-16h176a8 8 0 0 1 8 8"
                            />
                          </svg>
                        </button>
                      </div>
                    </div>
                    <div
                      class="flex items-center border-b p-2.5 justify-between"
                    >
                      <span class="font-semibold">نوزاد</span>
                      <div class="flex items-center gap-2">
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 24 24"
                          >
                            <path
                              fill="currentColor"
                              d="M19 12.998h-6v6h-2v-6H5v-2h6v-6h2v6h6z"
                            />
                          </svg>
                        </button>
                        <span>0</span>
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500 opacity-50"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 256 256"
                          >
                            <path
                              fill="currentColor"
                              d="M224 128a8 8 0 0 1-8 8H40a8 8 0 0 1 0-16h176a8 8 0 0 1 8 8"
                            />
                          </svg>
                        </button>
                      </div>
                    </div>
                    <div class="flex items-center gap-2 p-2.5">
                      <button
                        @click="PassengerHotel = false"
                        class="rounded-lg w-full flex items-center justify-center px-2.5 py-2 text-white bg-blue-500"
                      >
                        تایید
                      </button>
                      <button
                        @click="PassengerHotel = false"
                        class="rounded-lg w-full flex items-center justify-center px-2.5 py-2 text-blue-500 border-2 border-blue-500"
                      >
                        انصراف
                      </button>
                    </div>
                  </div>
                </TransitionExpand>
              </div>
            </div>

            <button class="btn-primary px-10">جستجو</button>
          </div>
        </div>
        <div v-if="step == 3" class="flex flex-col gap-5">
          <div class="flex flex-col lg:flex-row gap-2">
            <div
              class="justify-center flex flex-col gap-5 lg:gap-0 lg:flex-row relative"
            >
              <input
                type="text"
                placeholder="مبدا"
                class="border border-[#DCDFE4] px-6 py-[10px] rounded-2xl outline-blue-300"
              />

              <button type="button" class="h-full">
                <Icon
                  name="humbleicons:exchange-horizontal"
                  class="w-[50px] rotate-90 lg:rotate-0 h-[50px] rounded-[50%] absolute bg-white border-2 left-5 lg:-translate-x-1/2 lg:left-1/2 -translate-y-1/2 top-1/2 p-3 flex justify-center items-center"
                />

                <input
                  class="border h-full border-[#DCDFE4] px-5 placeholder:px-3 w-full py-[10px] rounded-2xl outline-blue-300"
                  type="text"
                  placeholder="مقصد"
                />
              </button>
            </div>
            <div
              v-click-outside="clickOutPassengerVisa"
              class="rounded-[16px] flex-grow relative border border-[#DCDFE4] px-6 py-[10px] cursor-pointer"
            >
              <div @click="PassengerVisa = !PassengerVisa">
                <p class="text-sm text-[#938F96]">مسافران</p>
                <p class="font-bold">2 بزرگسال - 1 کودک</p>
              </div>
              <div
                class="absolute bottom-0 left-0 top-16 z-50 h-max w-full bg-white shadow-xl rounded-lg px-4"
              >
                <TransitionExpand :duration="500">
                  <div
                    v-if="PassengerVisa"
                    class="flex flex-col rounded-lg z-50 bg-white shadow w-full absolute right-0 top-0"
                  >
                    <div
                      class="flex items-center border-b p-2.5 justify-between"
                    >
                      <span class="font-semibold">بزگسال</span>
                      <div class="flex items-center gap-2">
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 24 24"
                          >
                            <path
                              fill="currentColor"
                              d="M19 12.998h-6v6h-2v-6H5v-2h6v-6h2v6h6z"
                            />
                          </svg>
                        </button>

                        <span>0</span>
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500 opacity-50"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 256 256"
                          >
                            <path
                              fill="currentColor"
                              d="M224 128a8 8 0 0 1-8 8H40a8 8 0 0 1 0-16h176a8 8 0 0 1 8 8"
                            />
                          </svg>
                        </button>
                      </div>
                    </div>
                    <div
                      class="flex items-center border-b p-2.5 justify-between"
                    >
                      <span class="font-semibold">کودک</span>
                      <div class="flex items-center gap-2">
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 24 24"
                          >
                            <path
                              fill="currentColor"
                              d="M19 12.998h-6v6h-2v-6H5v-2h6v-6h2v6h6z"
                            />
                          </svg>
                        </button>
                        <span>0</span>

                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500 opacity-50"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 256 256"
                          >
                            <path
                              fill="currentColor"
                              d="M224 128a8 8 0 0 1-8 8H40a8 8 0 0 1 0-16h176a8 8 0 0 1 8 8"
                            />
                          </svg>
                        </button>
                      </div>
                    </div>
                    <div
                      class="flex items-center border-b p-2.5 justify-between"
                    >
                      <span class="font-semibold">نوزاد</span>
                      <div class="flex items-center gap-2">
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 24 24"
                          >
                            <path
                              fill="currentColor"
                              d="M19 12.998h-6v6h-2v-6H5v-2h6v-6h2v6h6z"
                            />
                          </svg>
                        </button>
                        <span>0</span>
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500 opacity-50"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 256 256"
                          >
                            <path
                              fill="currentColor"
                              d="M224 128a8 8 0 0 1-8 8H40a8 8 0 0 1 0-16h176a8 8 0 0 1 8 8"
                            />
                          </svg>
                        </button>
                      </div>
                    </div>
                    <div class="flex items-center gap-2 p-2.5">
                      <button
                        @click="PassengerVisa = false"
                        class="rounded-lg w-full flex items-center justify-center px-2.5 py-2 text-white bg-blue-500"
                      >
                        تایید
                      </button>
                      <button
                        @click="PassengerVisa = false"
                        class="rounded-lg w-full flex items-center justify-center px-2.5 py-2 text-blue-500 border-2 border-blue-500"
                      >
                        انصراف
                      </button>
                    </div>
                  </div>
                </TransitionExpand>
              </div>
            </div>

            <button class="btn-primary px-10">جستجو</button>
          </div>
        </div>
        <div v-if="step == 4" class="flex flex-col gap-5">
          <div class="flex flex-col lg:flex-row gap-2">
            <!-- ssdfds -->
            <div
              v-click-outside="clickOutCountryBimeh"
              class="rounded-[16px] flex-grow relative border border-[#DCDFE4] px-6 py-[10px] cursor-pointer"
            >
              <div @click="CountryBimeh = !CountryBimeh">
                <p class="text-sm text-[#938F96]">کشور مقصد</p>
                <p class="font-bold">نجف,عراق</p>
              </div>
              <div
                class="absolute bottom-0 left-0 top-16 z-50 h-max w-full bg-white shadow-xl rounded-lg px-4"
              >
                <TransitionExpand :duration="500">
                  <div
                    v-if="CountryBimeh"
                    class="flex flex-col rounded-lg px-5 w-full z-50 bg-white shadow absolute right-0 top-0"
                  >
                    <span
                      v-for="(item, index) in 6"
                      :key="index"
                      class="border-b py-2"
                      >دبی</span
                    >
                  </div>
                </TransitionExpand>
              </div>
            </div>
            <div
              @click="TimeTravelBimeh = !TimeTravelBimeh"
              v-click-outside="clickOutTimeTravelBimeh"
              class="rounded-[16px] flex-grow relative border border-[#DCDFE4] px-6 py-[10px] cursor-pointer"
            >
              <p class="text-sm text-[#938F96]">مدت سفر</p>
              <p class="font-bold">14 روز</p>
              <div
                class="absolute bottom-0 left-0 top-16 z-50 h-max w-full bg-white shadow-xl rounded-lg px-4"
              >
                <TransitionExpand :duration="500">
                  <div
                    v-if="TimeTravelBimeh"
                    class="flex flex-col rounded-lg px-5 w-full z-50 bg-white shadow absolute right-0 top-0"
                  >
                    <span
                      v-for="(item, index) in 6"
                      :key="index"
                      class="border-b py-2"
                      >1 تا 4 روز</span
                    >
                  </div>
                </TransitionExpand>
              </div>
            </div>
            <div
              v-click-outside="clickOutPassengerBimeh"
              class="rounded-[16px] flex-grow relative border border-[#DCDFE4] px-6 py-[10px] cursor-pointer"
            >
              <div @click="PassengerBimeh = !PassengerBimeh">
                <p class="text-sm text-[#938F96]">مسافران</p>
                <p class="font-bold">2 بزرگسال - 1 کودک</p>
              </div>
              <div
                class="absolute bottom-0 left-0 top-16 z-50 h-max w-full bg-white shadow-xl rounded-lg px-4"
              >
                <TransitionExpand :duration="500">
                  <div
                    v-if="PassengerBimeh"
                    class="flex flex-col rounded-lg z-50 bg-white shadow w-full absolute right-0 top-0"
                  >
                    <div
                      class="flex items-center border-b p-2.5 justify-between"
                    >
                      <span class="font-semibold">بزگسال</span>
                      <div class="flex items-center gap-2">
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 24 24"
                          >
                            <path
                              fill="currentColor"
                              d="M19 12.998h-6v6h-2v-6H5v-2h6v-6h2v6h6z"
                            />
                          </svg>
                        </button>

                        <span>0</span>
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500 opacity-50"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 256 256"
                          >
                            <path
                              fill="currentColor"
                              d="M224 128a8 8 0 0 1-8 8H40a8 8 0 0 1 0-16h176a8 8 0 0 1 8 8"
                            />
                          </svg>
                        </button>
                      </div>
                    </div>
                    <div
                      class="flex items-center border-b p-2.5 justify-between"
                    >
                      <span class="font-semibold">کودک</span>
                      <div class="flex items-center gap-2">
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 24 24"
                          >
                            <path
                              fill="currentColor"
                              d="M19 12.998h-6v6h-2v-6H5v-2h6v-6h2v6h6z"
                            />
                          </svg>
                        </button>
                        <span>0</span>

                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500 opacity-50"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 256 256"
                          >
                            <path
                              fill="currentColor"
                              d="M224 128a8 8 0 0 1-8 8H40a8 8 0 0 1 0-16h176a8 8 0 0 1 8 8"
                            />
                          </svg>
                        </button>
                      </div>
                    </div>
                    <div
                      class="flex items-center border-b p-2.5 justify-between"
                    >
                      <span class="font-semibold">نوزاد</span>
                      <div class="flex items-center gap-2">
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 24 24"
                          >
                            <path
                              fill="currentColor"
                              d="M19 12.998h-6v6h-2v-6H5v-2h6v-6h2v6h6z"
                            />
                          </svg>
                        </button>
                        <span>0</span>
                        <button
                          class="rounded-lg flex items-center justify-center p-2.5 text-white bg-blue-500 opacity-50"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="1em"
                            height="1em"
                            viewBox="0 0 256 256"
                          >
                            <path
                              fill="currentColor"
                              d="M224 128a8 8 0 0 1-8 8H40a8 8 0 0 1 0-16h176a8 8 0 0 1 8 8"
                            />
                          </svg>
                        </button>
                      </div>
                    </div>
                    <div class="flex items-center gap-2 p-2.5">
                      <button
                        @click="PassengerBimeh = false"
                        class="rounded-lg w-full flex items-center justify-center px-2.5 py-2 text-white bg-blue-500"
                      >
                        تایید
                      </button>
                      <button
                        @click="PassengerBimeh = false"
                        class="rounded-lg w-full flex items-center justify-center px-2.5 py-2 text-blue-500 border-2 border-blue-500"
                      >
                        انصراف
                      </button>
                    </div>
                  </div>
                </TransitionExpand>
              </div>
            </div>

            <button class="btn-primary px-10">جستجو</button>
          </div>
        </div>
      </section>
    </div>
  </section>
</template>

<script setup>
import { useScreens } from "vue-screen-utils";
const router = useRouter();
const step = ref(1);
// calender
const months = ref([
  "Jan",
  "Feb",
  "March",
  "April",
  "May",
  "June",
  "July",
  "August",
  "Sep",
  "Oct",
  "Nov",
  "Dec",
]);
const { mapCurrent } = useScreens({
  xs: "0px",
  sm: "640px",
  md: "768px",
  lg: "1024px",
});
const columns = mapCurrent({ lg: 2 }, 1);
const expanded = mapCurrent({ lg: false }, true);
const range = ref({
  start: Date.now(),
  end: Date.now(),
});
const cancelAndResetCalender = () => {
  firstDate.value = false;
  range.value = {
    start: new Date(Date.now()),
    end: new Date(Date.now()),
  };
};

// Air
const way = ref(false);
const clickOutWay = () => {
  if (way.value) {
    way.value = false;
  }
};
const financial = ref(false);
const clickOutfinancial = () => {
  if (financial.value) {
    financial.value = false;
  }
};
const PassengerAir = ref(false);
const clickOutPassengerAir = () => {
  if (PassengerAir.value) {
    PassengerAir.value = false;
  }
};
const dateAir = ref(false);
const clickOutdateAir = () => {
  if (dateAir.value) {
    dateAir.value = false;
  }
};

// Hotel
const destinationHotel = ref(false);
const clickOutdestinationHotel = () => {
  if (destinationHotel.value) {
    destinationHotel.value = false;
  }
};
const PassengerHotel = ref(false);
const clickOutPassengerHotel = () => {
  if (PassengerHotel.value) {
    PassengerHotel.value = false;
  }
};
const dateHotelOrigin = ref(false);
const clickOutdateHotelOrigin = () => {
  if (dateHotelOrigin.value) {
    dateHotelOrigin.value = false;
  }
};
const dateHotelDest = ref(false);
const clickOutdateHotelDest = () => {
  if (dateHotelDest.value) {
    dateHotelDest.value = false;
  }
};

// Visa
const PassengerVisa = ref(false);
const clickOutPassengerVisa = () => {
  if (PassengerVisa.value) {
    PassengerVisa.value = false;
  }
};

// bimeh
const CountryBimeh = ref(false);
const clickOutCountryBimeh = () => {
  if (CountryBimeh.value) {
    CountryBimeh.value = false;
  }
};
const TimeTravelBimeh = ref(false);
const clickOutTimeTravelBimeh = () => {
  if (TimeTravelBimeh.value) {
    TimeTravelBimeh.value = false;
  }
};
const PassengerBimeh = ref(false);
const clickOutPassengerBimeh = () => {
  if (PassengerBimeh.value) {
    PassengerBimeh.value = false;
  }
};
</script>

<style scoped>
:deep(.vc-bordered) {
  @apply !border-none;
}
</style>
