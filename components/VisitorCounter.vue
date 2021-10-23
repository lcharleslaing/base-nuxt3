<template>
  <div
    class="flex items-center px-4 m-2 text-lg font-bold text-white rounded-lg shadow-sm "
    id="count"
  ></div>
</template>

<script>
export default {
  mounted() {
    const countEl = document.getElementById("count");

    updateVisitCount();

    function updateVisitCount() {
      fetch("https://api.countapi.xyz/update/localhost/leelaing?amount=1")
        .then((res) => res.json())
        .then((res) => {
          countEl.innerHTML = res.value;
        });
    }
  },
};
</script>

<style lang="scss" scoped>
</style>
