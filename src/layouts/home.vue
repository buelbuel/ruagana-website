<template>
  <div class="grid grid-cols-12 grid-flow-col text-gray-800 dark:text-gray-200 min-h-100vh">
    <div class="px-4 py-6 bg-gray-200 dark:bg-gray-700 col-span-2 flex flex-col">
      <Navigation />
      <Footer />
    </div>
    <main class="px-4 py-10 col-span-10">
      <router-view />
    </main>
  </div>
</template>
