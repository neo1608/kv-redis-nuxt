<template>
  <main
    class="relative flex flex-col items-center justify-center min-h-screen py-10"
  >
   
    <h1
      class="pt-4 pb-8 bg-gradient-to-br dark:from-white from-black via-[#707070] to-[#ffffff] bg-clip-text text-center text-4xl font-medium tracking-tight text-transparent md:text-7xl"
    >
      Monish Might use this View Component
    </h1>
    <div
      class="flex flex-col items-center w-full max-w-xl p-12 mx-auto rounded-lg shadow-xl dark:bg-white/10 bg-white/30 ring-1 ring-gray-900/5 backdrop-blur-lg"
    >
      <div class="mb-6 text-lg text-center">
        Displayed below is the total number of page views for this demo. Refresh
        the page and watch it increase!
      </div>
      <button
        @click="refreshPage()"
        class="mb-6 font-bold underline opacity-70 hover:opacity-100"
      >
        Refresh Page
      </button>
      <div class="text-5xl font-bold">{{ pageVisits?.pageVisits }}</div>
    </div>
    
  </main>
</template>

<script setup>
const { data: pageVisits } = await useFetch(() => `/api/kv-demo`)
const refreshPage = () => {
  window.location.reload()
}
</script>
