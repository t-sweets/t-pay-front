<template>
  <v-ons-navigator
    swipeable
    :page-stack="pageStack"
    @push-page="pageStack.push($event)"
    @pop-page="popPage($event)"
  ></v-ons-navigator>
</template>

<script>
import index from "~/pages/";

export default {
  // middleware: ["authenticated"],
  data() {
    return {
      pageStack: [index]
    };
  },
  methods: {
    popPage(event) {
      this.pageStack.unshift(event);
      this.pageStack.splice(1, this.pageStack.length - 1);
    }
  }
};
</script>


<style lang="scss">
html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

ons-page {
  text-align: center;
}
.toolbar {
  .toolbar__title {
    color: #4b9ad8;
  }
}
.tabbar {
  background-color: #fff !important;
}
</style>

