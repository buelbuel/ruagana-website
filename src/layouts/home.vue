<template>
  <div class="lg:grid lg:grid-cols-12 lg:grid-flow-col text-gray-800 dark:text-gray-200 min-h-100vh">
    <div class="p-6 bg-gray-200 dark:bg-gray-700 lg:col-span-2 flex flex-col">
      <Navigation />
      <Footer class="hidden lg:block" />
    </div>
    <main class="px-6 py-10 lg:col-span-10">
      <router-view />
    </main>
    <Footer class="block lg:hidden" />
  </div>
</template>
