<!-- Breakpoint: 425px, 768px, 1200px, and upper -->
<template>
  <div class=" py-lg-13 py-8">
    <HelloThere />
    <!-- Parallax for desktop, laptop -->
    <ParallaxImage title="Infinite black skies" aosValue='fade-left' src="/images/1.jpg"/>
    <ParallaxImageHeight title="we will stand tall" v-if="$mq === 'desktop'" aosValue='fade-right' left="114px" right="320px" src="/images/2.jpg"/>
    <ParallaxImageHeight title="we will stand tall" v-if="$mq !== 'desktop'" aosValue='fade-right' left="100px" right="190px" src="/images/2.jpg"/>
    <ParallaxImageHeight title="feel the earth move" v-if="$mq === 'desktop'" aosValue='fade-left' left="570px" right="114px" src="/images/3.jpg"/>
    <ParallaxImageHeight title="feel the earth move" v-if="$mq !== 'desktop'" aosValue='fade-left' left="475px" right="100px" src="/images/3.jpg"/>
    <ParallaxImage title="where worlds collide" aosValue='fade-right' left="0px" right="343px" src="/images/4.jpg"/>
    <!-- Parallax for mobile, tablet -->
    <ParallaxImageMobile title="Infinite black skies" aosValue='fade-left' src="/images/1.jpg"/>
    <ParallaxImageMobile title="we will stand tall" aosValue='fade-right'  src="/images/2.jpg"/>
    <ParallaxImageMobile title="feel the earth move"  aosValue='fade-left' src="/images/3.jpg"/>
    <ParallaxImageMobile title="where worlds collide" aosValue='fade-right' src="/images/4.jpg"/> 
    <Contact />
  </div>
</template>

<script>
import Vue from 'vue'
window.$ = window.jQuery = require('jquery');
import VueMq from 'vue-mq';

Vue.use(VueMq, {
  breakpoints: {
    mobile: 450,
    tablet: 768,
    laptop: 1024,
    desktop: Infinity,
  }
})

import HelloThere from '../components/HelloThere.vue';
import ParallaxImage from '../components/ParallaxImage.vue';
import ParallaxImageHeight  from '../components/ParallaxImageHeight.vue';
import ParallaxImageMobile  from '../components/ParallaxImageMobile.vue';
import Contact from '../components/Contact.vue';
export default {
  name: "MainContent",
//   data () {
//   return {
//     scrolled: false,
//   };
// },
// methods: {
//   handleScroll () {
//     var scrolledValue = this.scrolled;
//     scrolledValue = window.scrollY;
//     if(scrolledValue >200){
//       console.log(scrolledValue);
//     }
    
//   }
// },
// created () {
//   window.addEventListener('scroll', this.handleScroll);
// },
// destroyed () {
//   window.removeEventListener('scroll', this.handleScroll);
// },
  components: {
    HelloThere,
    ParallaxImage,
    ParallaxImageHeight,
    ParallaxImageMobile,
    Contact
    }
}
</script>

<style lang="scss" scoped>
@import "~@theme/styles/bootstrap/bootstrap";
</style>
