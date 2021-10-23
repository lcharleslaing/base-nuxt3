<template>
  <div class="p-4 m-2 text-lg font-bold rounded-lg" id="time_span"></div>
</template>

<script>
export default {
  mounted() {
    var today = new Date();
    var time =
      today.getHours() + ":" + today.getMinutes() + ":" + today.getSeconds();

    timer();

    function formatAMPM(date) {
      var hours = date.getHours();
      var minutes = date.getMinutes();
      var ampm = hours >= 12 ? "pm" : "am";
      hours = hours % 12;
      hours = hours ? hours : 12; // the hour '0' should be '12'
      minutes = minutes < 10 ? "0" + minutes : minutes;
      var strTime = hours + ":" + minutes;
      return strTime;
    }

    function timer() {
      var currentTime = new Date();
      var hours = currentTime.getHours();
      var pmhours = currentTime.getHours() - 12;
      var minutes = currentTime.getMinutes();
      if (minutes < 10) {
        minutes = "0" + minutes;
      }
      var t_str = pmhours + ":" + minutes;

      if (hours > 11) {
        t_str += " PM";
      } else {
        t_str += " AM";
      }
      document.getElementById("time_span").innerHTML = t_str;
      setTimeout(timer, 1000);
    }
  },
};
</script>

<style lang="scss" scoped>
</style>
