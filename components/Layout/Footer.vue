<template>
  <div class="border-t bg-white">
    <footer class="max-w-7xl  w-full mx-auto px-5 py-1 pb-5">
      <div class="grid gap-5 lg:gap-0 lg:grid-flow-col py-10">
        <main class="space-y-5">
          <h4 class="font-semibold text-lg">
            {{ $t("footer.title.services") }}
          </h4>
          <ul class="flex lg:flex-col justify-between lg:justify-start lg:gap-3">
            <li>{{ $t("footer.services.airTicket") }}</li>
            <li>{{ $t("footer.services.residence") }}</li>
            <li>{{ $t("footer.services.travel_insurance") }}</li>
            <li>{{ $t("footer.services.tourist_visa") }}</li>
          </ul>
        </main>
        <main class="space-y-5">
          <h4 class="font-semibold text-lg">
            {{ $t("footer.title.tourist_visa") }}
          </h4>

          <ul class="grid grid-rows-4 grid-cols-2 gap-3">
            <li>{{ $t("footer.tourist_visa.azarbaijan") }}</li>
            <li>{{ $t("footer.tourist_visa.qatar") }}</li>
            <li>{{ $t("footer.tourist_visa.canada") }}</li>
            <li>{{ $t("footer.tourist_visa.russia") }}</li>
            <li>{{ $t("footer.tourist_visa.dubai") }}</li>
            <li>{{ $t("footer.tourist_visa.oman") }}</li>
            <li>{{ $t("footer.tourist_visa.jordan") }}</li>
            <li>{{ $t("footer.tourist_visa.armania") }}</li>
          </ul>
        </main>
        <main class="space-y-5">
          <h4 class="font-semibold text-lg">
            {{ $t("footer.title.ticket_air") }}
          </h4>
          <div class="flex gap-5">
            <ul class="grid grid-rows-4 grid-cols-2 gap-3">
              <li>{{ $t("footer.ticket_air.thr_mhd") }}</li>
              <li>{{ $t("footer.ticket_air.mhd_njf") }}</li>
              <li>{{ $t("footer.ticket_air.thr_kish") }}</li>
              <li>{{ $t("footer.ticket_air.thr_istb") }}</li>
              <li>{{ $t("footer.ticket_air.njf_mhd") }}</li>
              <li>{{ $t("footer.ticket_air.thr_mqt") }}</li>
              <li>{{ $t("footer.ticket_air.ttr_thr") }}</li>
            </ul>
          </div>
        </main>
      </div>

      <div class="flex flex-col lg:flex-row justify-between gap-5 lg:gap-0 lg:items-center">
        <div class="flex gap-5 flex-col">
          <h5>{{ $t("footer.title.contact") }}</h5>
          <div class="flex gap-3 flex-col lg:flex-row">
            <div class="flex items-center gap-3">
              <Icon name="mage:phone-call" />
              <p class="rtl:flex-row-reverse flex gap-2">
                <span class="flex rtl:flex-row-reverse"><span>+</span>964</span
                ><span>780</span><span>814</span>
                <span>3063</span>
              </p>
            </div>
            <div class="flex items-center gap-3">
              <Icon name="ic:outline-email" />
              <p>CrsTrip.com@gmail.com</p>
            </div>
          </div>
        </div>

        <div class="flex gap-4 items-center">
          <NuxtLink to="/" class="p-2.5 rounded-lg bg-blue-500">
            <Icon name="mdi:instagram" color="white" size="2rem" />
          </NuxtLink>
          <NuxtLink to="/" class="p-2.5 rounded-lg bg-blue-500">
            <Icon name="mingcute:telegram-fill" color="white" size="2rem" />
          </NuxtLink>
          <NuxtLink to="/" class="p-2.5 rounded-lg bg-blue-500">
            <Icon name="ic:baseline-whatsapp" color="white" size="2rem" />
          </NuxtLink>
        </div>
      </div>
    </footer>
  </div>
  <div
    class="flex bg-white items-center rtl:flex-row-reverse justify-center gap-2 py-5 border-t w-full"
  >
    <Icon name="ic:baseline-copyright"/>
    <p class="text-sm text-end lg:text-center text-wrap text-[#1D1B20]">
      {{ $t("footer.copyright") }}
    </p>
  </div>
</template>

<script setup></script>
