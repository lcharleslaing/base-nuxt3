<template>
  <div
    class="
      flex
      items-center
      justify-center
      p-2
      bg-blue-700
      mx-3
      mt-0
      mb-1
      rounded-b-lg
    "
  >
    <div
      class="
        text-center text-white text-2xl
        font-extrabold
        py-0
        px-4
        bordered
        shadow-sm
        rounded-lg
      "
    >
      {{ pagetitle }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: ["pagetitle", "titlecolor"],
};
</script>

<style lang="scss" scoped>
</style>
