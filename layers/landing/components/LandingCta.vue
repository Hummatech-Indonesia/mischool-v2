<template>
  <div class="dark:bg-muted-900 bg-white py-24">
    <div class="mx-auto w-full max-w-7xl px-4">
      <div class="mx-auto w-full max-w-6xl">
        <div
          class="bg-primary-900 dark:bg-primary-900/40 ltablet:grid ltablet:grid-cols-2 ltablet:gap-4 overflow-hidden rounded-3xl shadow-xl lg:grid lg:grid-cols-2 lg:gap-4"
        >
          <div
            class="ltablet:py-28 ltablet:pr-0 flex items-center px-6 pb-12 pt-10 sm:px-16 sm:pt-16 lg:py-28 lg:pr-0 xl:px-20"
          >
            <div class="ltablet:self-center font-sans lg:self-center">
              <h2 class="text-3xl font-medium text-white sm:text-4xl">
                <span class="block">Siap Untuk Mempelajari Lebih Dalam?</span>
              </h2>
              <p class="mt-4 text-lg leading-6 text-white">
                Kami membangun dokumentasi komplex yang memudahkan setiap
                pengguna dalam menggunakan sistem kami.
              </p>
              <div class="mt-8 flex items-center gap-2">
                <BaseButton to="/documentation" shape="curved" class="!h-11"
                  >Buka Dokumentasi</BaseButton
                >
              </div>
            </div>
          </div>
          <div class="aspect-w-5 aspect-h-3 md:aspect-w-2 md:aspect-h-1 -mt-6">
            <img
              class="ltablet:translate-y-20 block translate-x-6 translate-y-6 rounded-md object-cover object-left-top sm:translate-x-16 lg:translate-y-20"
              src="/img/illustrations/people.svg"
              alt="Mischool demo screenshot"
              width="568"
              height="532"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
