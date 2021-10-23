<template>
  <div class="flex justify-between w-screen bg-gray-800 h-14">
    <!-- menu & logo -->
    <div class="flex items-center">
      <!-- heroicons menu icon vertically centered-->
      <div
        class="flex items-center p-2 m-4 rounded-lg menu_icon hover:bg-gray-700"
      >
        <Icon name="menu" class="text-white" />
      </div>
      <!-- logo image ninja-svelte.png -->
      <NuxtLink to="/">
        <img class="h-10 w-14" src="ninja-svelte.png" />
      </NuxtLink>
    </div>
    <LiveClock class="flex items-center text-white" />
    <!-- Links -->
    <div
      class="flex items-center justify-between gap-2 font-bold text-white  sm:hidden"
    >
      <NuxtLink class="p-2 rounded-lg hover:bg-gray-700" to="/">Home</NuxtLink>
      <NuxtLink class="p-2 rounded-lg hover:bg-gray-700" to="/blog"
        >Blog</NuxtLink
      >
      <NuxtLink class="p-2 rounded-lg hover:bg-gray-700" to="/about"
        >About</NuxtLink
      >
      <NuxtLink class="p-2 rounded-lg hover:bg-gray-700" to="/contact"
        >Contact</NuxtLink
      >
    </div>
    <VisitorCounter class="text-white" />

    <!-- searchbar & menu -->
    <div class="flex items-center mr-6">
      <!-- search bar -->
      <div class="flex items-center m-4 md:hidden">
        <!-- search icon -->
        <Icon name="search" />
        <input
          class="w-full h-8 px-2 text-gray-900 bg-gray-200 rounded-lg shadow-outline  focus:outline-none focus"
          type="text"
          placeholder="Search"
        />
      </div>
      <!-- right menu icon -->
      <div
        class="flex items-center justify-end p-2 text-white rounded-lg  hover:bg-gray-700"
      >
        <Icon name="vert-dots" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "NavigationBar",
  data() {
    return {
      //
    };
  },
  methods: {
    //
  },
};
</script>

<style scoped>
</style>
