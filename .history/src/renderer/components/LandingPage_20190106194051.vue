<template>
  <div id="wrapper">
    <TitleBar></TitleBar>
    <main>
      <div class="left-side">
        <span class="titlesize">Welcome to terminally</span>
        <system-information></system-information>
      </div>

      <div class="right-side">
        <div class="doc">
          <div class="titlesize">Getting Started</div>
          <button @click="open('https://simulatedgreg.gitbooks.io/electron-vue/content/')">Read the Docs</button>
          <br>
          <br>
        </div>
        <div class="doc">
          <div class="titlesize alt">Other Documentation</div>
          <button class="alt"
                  @click="open('https://electron.atom.io/docs/')">Electron</button>
          <button class="alt"
                  @click="open('https://vuejs.org/v2/guide/')">Vue.js</button>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
import SystemInformation from "./LandingPage/SystemInformation";
import TitleBar from "./UI/TitleBar";
export default {
  name: "landing-page",
  components: {
    SystemInformation,
    TitleBar
  },

  methods: {
    open (link) {
      this.$electron.shell.openExternal(link);
    },
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Source+Sans+Pro");

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: "Source Sans Pro", sans-serif;
}

#wrapper {
  background: radial-gradient(
    ellipse at top left,
    rgba(255, 255, 255, 1) 40%,
    rgba(229, 229, 229, 0.9) 100%
  );
  height: 100vh;
  padding: 0px 0px 0px 0px;
  width: 100vw;
}

#titlebar {
  display: flex;
  flex-wrap: nowrap;
  height: 100%;
  width: 100%;
}

#logo {
  -webkit-user-select: none;
  -webkit-app-region: drag;
}

#title {
  height: 100%;
  width: 100%;
  -webkit-user-select: none;
  -webkit-app-region: drag;
  display: flex;
  justify-content: center;
  align-items: center;
}

#mouseOver {
  background-color: #cccccc;
  width: 40px;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  -webkit-user-select: none;
}

#mouseLeave {
  background-color: transparent;
  width: 40px;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  -webkit-user-select: none;
}
#CLOSEmouseOver {
  background-color: #ff0000;
  width: 40px;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  -webkit-user-select: none;
}

#CLOSEmouseLeave {
  background-color: transparent;
  width: 40px;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  -webkit-user-select: none;
}
#menu {
  height: 100%;
  width: auto;
  -webkit-user-select: none;
  display: flex;
  justify-content: center;
  align-items: center;
}
main {
  display: flex;
  height: 90%;
  justify-content: center;
  align-items: center;
}

main > div {
  flex-basis: 50%;
}

.left-side {
  display: flex;
  height: 100%;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.welcome {
  color: #555;
  font-size: 23px;
  margin-bottom: 10px;
}

.titlesize {
  color: #2c3e50;
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 6px;
}

.titlesize.alt {
  font-size: 18px;
  margin-bottom: 10px;
}

.doc p {
  color: black;
  margin-bottom: 10px;
}

.doc button {
  font-size: 0.8em;
  cursor: pointer;
  outline: none;
  padding: 0.75em 2em;
  border-radius: 2em;
  display: inline-block;
  color: #fff;
  background-color: #4fc08d;
  transition: all 0.15s ease;
  box-sizing: border-box;
  border: 1px solid #4fc08d;
}

.doc button.alt {
  color: #42b983;
  background-color: transparent;
}
</style>