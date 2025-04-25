<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <input type="text" placeholder="google帳號" />
    <input type="text" placeholder="起始日期" />
    <input type="text" placeholder="結束日期" />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: "app",
  components: {
    // HelloWorld
  },
  data() {
    return {};
  },
  created() {
    let xhr = new XMLHttpRequest();

    xhr.open("GET", "https://clients6.google.com/calendar/v3/calendars/yangfan.tec.13%40gmail.com/events?eventTypes=default&eventTypes=focusTime&eventTypes=outOfOffice&singleEvents=true&timeZone=Asia%2FTaipei&calendarId=yangfan.tec.13%40gmail.com&maxResults=999&timeMin=2025-04-01T00%3A00%3A00.000%2B08%3A00&timeMax=2025-08-20T00%3A00%3A00.000%2B08%3A00&key=AIzaSyBNlYH01_9Hc5S1J9vuFmu2nUqBZJNAXxs&orderBy=startTime");

    xhr.responseType = "json";

    xhr.send();

    // the response is {"message": "Hello, world!"}
    xhr.onload = function () {
      let responseObj = xhr.response;
      // eslint-disable-next-line no-console
      console.log(responseObj)
    };
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
