<template>
  <div id="app">
    <toor-bar></toor-bar>
    <transition  name= "fade">
    <router-view></router-view>
    </transition>
  </div>
</template>

<script>
import ToorBar from "./components/Toolbar.vue";
export default {
  components: {
    ToorBar,
  },
};
</script>

<style>
#app {
}
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to
 /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
