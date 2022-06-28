<script setup>
import Header from './components/Header.vue'
import Sidebar from './components/Sidebar.vue'
import Main from './components/Main.vue'
import Javascript from './components/Javascript.vue';
import Css from './components/Css.vue'
import Html from './components/Html.vue'
</script>

<template>  
  <div class="text-yellow-100">
    <Header v-if="!jsToggle && !cssToggle && !htmlToggle" :titles="['Main Page']"/>
    <Javascript v-if="jsToggle" />
    <Css v-if="cssToggle" />
    <Html v-if="htmlToggle" />
    <Sidebar
      @cssClicked="cssClicked"
      @htmlClicked="htmlClicked"
      @jsClicked="jsClicked"
    />
    <Main />
  </div> 
</template>

<script>
  export default {
    data() {
      return {
        jsToggle: false,
        cssToggle: false,
        htmlToggle: false,
      }
    },
    methods: {
      cssClicked() {
        this.cssToggle = true
        this.jsToggle = false
        this.htmlToggle = false
      },
      jsClicked() {
        this.cssToggle = false
        this.jsToggle = true
        this.htmlToggle = false
      },
      htmlClicked() {
        this.cssToggle = false
        this.jsToggle = false
        this.htmlToggle = true
      },
    },
  }
</script>
