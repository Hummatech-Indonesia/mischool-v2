<!-- eslint-disable prettier-vue/prettier -->
<script setup lang="ts">
const { x, y } = useWindowScroll()
const isSearchOpen = useState('search-open', () => false)
const isMobileOpen = ref(false)

const metaKey = useMetaKey()
const { open } = usePanels()
</script>

<!-- eslint-disable prettier-vue/prettier -->
<template>
  <div
    class="group/nav ltablet:max-w-[1000px] ptablet:max-w-[47rem] fixed inset-x-0 top-0 z-50 mx-auto max-w-[350px] group-[&.scrolled]/landing:mt-2 group-[&:not(.scrolled)]/landing:mt-4 motion-safe:transition-all motion-safe:duration-200 lg:max-w-7xl">
    <div
      class="group-[&.scrolled]/landing:dark:bg-muted-950/95 group-[&.scrolled]/landing:border-muted-200 group-[&.scrolled]/landing:dark:border-muted-700 group-[&.scrolled]/landing:motion-safe:shadow-muted-300/30 group-[&.scrolled]/landing:motion-safe:dark:shadow-muted-800/20 flex items-center justify-between rounded-2xl border p-4 group-[&:not(.scrolled)]/landing:border-transparent group-[&.scrolled]/landing:bg-white/95 motion-safe:transition-all motion-safe:duration-200 group-[&.scrolled]/landing:motion-safe:shadow-xl">
      <div class="flex w-1/2 items-center gap-2 md:w-1/5">
        <NuxtLink to="/" class="ms-2 inline-flex" aria-label="Go to Tairo homepage">
          <TairoLogoText
            class="text-primary-500 group-[&.scrolled]/landing:h-6 group-[&:not(.scrolled)]/landing:h-7 motion-safe:transition-all motion-safe:duration-200" />
        </NuxtLink>
      </div>
      <div
        class="ltablet:static ltablet:w-auto ltablet:flex ltablet:flex-row dark:bg-muted-950 ltablet:!bg-transparent ltablet:mx-0 fixed inset-x-0 top-20 mx-auto w-[calc(100%_-_2rem)] items-center justify-center bg-white lg:static lg:mx-0 lg:flex lg:w-auto lg:flex-row lg:!bg-transparent"
        :class="[
          isMobileOpen
            ? 'shadow-muted-300/30 dark:shadow-muted-900/20 group-[&.scrolled]/landing:ltablet:mt-0 group-[&:not(.scrolled)]/landing:ltablet:mt-0 flex flex-col space-y-4 rounded-xl p-6 shadow-xl group-[&.scrolled]/landing:mt-2 group-[&:not(.scrolled)]/landing:mt-4 motion-safe:transition-all motion-safe:duration-200 group-[&.scrolled]/landing:lg:mt-0 group-[&:not(.scrolled)]/landing:lg:mt-0'
            : 'hidden',
        ]">
        <NuxtLink to="/preview" class="inline-flex items-center justify-center px-6">
          Preview
        </NuxtLink>
        <NuxtLink to="/berita" class="inline-flex items-center justify-center px-6">
          Berita
        </NuxtLink>
        <NuxtLink to="/docs" class="inline-flex items-center justify-center px-6">
          Dokumentasi
        </NuxtLink>
        <NuxtLink to="/contact" class="inline-flex items-center justify-center px-6">
          Kontak
        </NuxtLink>
        <div class="px-6">
          <button type="button"
            class="group-[&.scrolled]/landing:bg-muted-100 group-[&.scrolled]/landing:dark:bg-muted-900 group-[&.scrolled]/landing:border-muted-100 group-[&.scrolled]/landing:dark:border-muted-800 group-[&.scrolled]/landing:text-muted-400 group-[&.scrolled]/landing:dark:text-muted-500 group-[&.scrolled]/landing:hover:text-primary-500 group-[&.scrolled]/landing:dark:hover:text-primary-500 group-[&:not(.scrolled)]/landing:text-muted-800 group-[&:not(.scrolled)]/landing:dark:text-muted-200 group flex items-center gap-2 rounded-xl py-1 pe-1 ps-3 group-[&.scrolled]/landing:border"
            @click="isSearchOpen = true" aria-label="Open search">
            <Icon name="lucide:search" class="h-4 w-4 motion-safe:transition-colors motion-safe:duration-300" />
            <span
              class="group-[&.scrolled]/landing:dark:bg-muted-800 group-[&.scrolled]/landing:border-muted-200 group-[&.scrolled]/landing:dark:border-muted-700 group-[&.scrolled]/landing:group-hover:text-muted-600 group-[&.scrolled]/landing:dark:group-hover:text-muted-100 rounded-lg border px-2 py-0.5 group-[&:not(.scrolled)]/landing:border-transparent group-[&.scrolled]/landing:bg-white group-[&.scrolled]/landing:shadow motion-safe:transition-colors motion-safe:duration-300">
              <kbd class="font-sans text-sm tracking-wide">
                {{ metaKey }} + k
              </kbd>
            </span>
          </button>
        </div>
        <div class="px-6">
          <BaseButton v-if="isMobileOpen" shape="curved" color="primary" to="https://school.Mischool.id/login">
            Login
          </BaseButton>
        </div>
      </div>
      <div class="flex w-1/2 items-center justify-end gap-4 md:w-1/5">
        <button type="button"
          class="border-muted-200 hover:ring-muted-200 dark:hover:ring-muted-700 dark:border-muted-700 dark:bg-muted-800 dark:ring-offset-muted-900 flex h-9 w-9 items-center justify-center rounded-full border bg-white ring-1 ring-transparent transition-all duration-300 hover:ring-offset-4"
          @click="() => {
            const isOpen = useState('switcher-open', () => false)
            isOpen.value = true
          }
          ">
          <Icon name="ph:drop-half-bottom-duotone" class="text-muted-400 h-5 w-5" />
        </button>
        <BaseThemeToggle aria-label="Toggle darkmode" />
        <BaseButton shape="curved" color="primary" to="https://school.Mischool.id/login"
          class="ltablet:!flex !hidden lg:!flex">
          Login
        </BaseButton>
        <button type="button" class="ltablet:hidden flex items-center justify-center lg:hidden"
          @click="isMobileOpen = !isMobileOpen" :aria-label="isMobileOpen ? 'Close menu' : 'Open menu'">
          <div class="space-y-1.5">
            <span class="bg-primary-600 block h-0.5 motion-safe:transition-all motion-safe:duration-300"
              :class="isMobileOpen ? 'w-2' : 'w-6'"></span>
            <span class="bg-primary-600 block h-0.5 motion-safe:transition-all motion-safe:duration-300"
              :class="isMobileOpen ? 'w-6' : 'w-6'"></span>
            <span class="bg-primary-600 block h-0.5 motion-safe:transition-all motion-safe:duration-300"
              :class="isMobileOpen ? 'w-4' : 'w-6'"></span>
          </div>
        </button>
      </div>
    </div>
  </div>
</template>
