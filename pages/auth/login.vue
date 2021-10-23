<template>
  <div>
    <PageTitle name="Login Page" />
  </div>
</template>

<script>
export default {
  // create a function that returns the date and time in the format of DD-MM-YYYY HH:MM:SS
  created() {
    this.dateTime = this.getDateTime();
  },
  methods: {
    getDateTime() {
      let date = new Date();
      let year = date.getFullYear();
      let month = date.getMonth() + 1;
      let day = date.getDate();
      let hour = date.getHours();
      let min = date.getMinutes();
      let sec = date.getSeconds();

      month = (month < 10 ? "0" : "") + month;
      day = (day < 10 ? "0" : "") + day;
      hour = (hour < 10 ? "0" : "") + hour;
      min = (min < 10 ? "0" : "") + min;
      sec = (sec < 10 ? "0" : "") + sec;

      return (
        day + "-" + month + "-" + year + " " + hour + ":" + min + ":" + sec
      );
    },
  },
};
</script>

<style lang="scss" scoped>
</style>
