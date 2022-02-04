<template>
  <div class="grid grid-cols-12 grid-flow-col text-gray-800 dark:text-gray-200">
    <div class="px-4 py-6 bg-gray-200 dark:bg-gray-700 col-span-2 flex flex-col">
      <Navigation />
      <Footer />
    </div>
    <aside class="px-4 py-6 bg-gray-100 dark:bg-gray-800 col-span-2">
      <wiki-navigation />
    </aside>
    <main class="px-4 py-10 col-span-8">
      <router-view />
    </main>
  </div>
</template>
