<template>
  <div id="app">
    <video id="myMainVideoPlayer" controls></video>
  </div>
</template>

<script>
import { MediaPlayer } from "dashjs";

export default {
  data() {
    return {
      url: "https://dash.akamaized.net/akamai/bbb_30fps/bbb_30fps.mpd",
    };
  },
  methods: {
    calculateNumber() {
      let num = 0;
      for (let i = 0; i < 10000000000; i++) {
        num = num + i;
      }
      for (let i = 0; i < 10000000000; i++) {
        num = num + i;
      }
      for (let i = 0; i < 10000000000; i++) {
        num = num + i;
      }
      for (let i = 0; i < 10000000000; i++) {
        num = num + i;
      }
    },
  },
  mounted() {
    const player = MediaPlayer().create();
    player.initialize(
      document.querySelector("#myMainVideoPlayer"),
      this.url,
      true
    );
    setTimeout(this.calculateNumber, 10000);
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
