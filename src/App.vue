<template>
  <div id="app">
    <div class="date">
      <div>
        <span>{{today}}</span>
      </div>
      <div>
        <span>{{date}}</span>
      </div>
      <div class="result">
        <span>{{result}} Hari Lagi</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      date: "",
      today: "",
      result: ""
    };
  },
  created() {
    this.count();
  },
  methods: {
    count() {
      let now = new Date();
      let target = new Date(2019, 5, 7);
      let dayNow = new Date(2019, 5, 7);
      let day = 42;

      // now
      let nDate = now.getDate();
      let nMonth = now.getMonth() + 1;
      let nYear = now.getFullYear();

      // target
      let tDate = target.getDate();
      let tMonth = target.getMonth() + 1;
      let tYear = target.getFullYear();

      this.today = nDate + " - " + nMonth + " - " + nYear;
      this.date = tDate + " - " + tMonth + " - " + tYear;

      let hasil = target - now;

      let days = hasil / 85074349;

      // myDate = new Date(1000 * hasil);

      this.result = days.toFixed();
    }
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

.date {
  position: absolute;
  top: 50%;
  transform: translate(-50%, -50%);
  left: 50%;

  .result {
    margin-top: 10px;
  }
}
</style>
