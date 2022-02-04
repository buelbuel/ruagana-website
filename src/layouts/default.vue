<template>
  <div class="lg:grid lg:grid-cols-12 lg:grid-flow-col text-gray-800 dark:text-gray-200">
    <div class="p-6 bg-gray-200 dark:bg-gray-700 lg:col-span-2 flex flex-col">
      <Navigation />
      <Footer class="hidden lg:block" />
    </div>
    <aside class="p-6 bg-gray-100 dark:bg-gray-800 lg:col-span-2">
      <wiki-navigation />
    </aside>
    <main class="px-6 py-10 lg:col-span-8">
      <router-view />
    </main>
    <Footer class="block lg:hidden" />
  </div>
</template>
