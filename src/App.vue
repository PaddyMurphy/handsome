<template>
  <div id="app">

    <label class="menu-label">
      <button @click="toggleMenu" class="button menu-link">
        <svg width="13px" height="10px" viewBox="0 0 13 10" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
            <g class="icon-menu-open" fill-rule="evenodd" stroke-linecap="square">
                <path d="M0,1 L10.9655725,1"></path>
                <path d="M0,5 L8,5"></path>
                <path d="M0,9 L10.9655725,9"></path>
            </g>
        </svg>
      </button> <b>Menu</b>
    </label>
    <!-- Do not dynamically create menu. This needs to be
         implemented in a static page -->
    <ul class="menu-primary">
      <li><a href="">Becoming a Student</a></li>
      <li><a href="">Current Students</a></li>
      <li><a href="">Parents & Family</a></li>
      <li><a href="">Faculty & Staff</a></li>
      <li><a href="">Alumni</a></li>
    </ul>

    <ul class="menu-secondary is-hidden">
      <li><a href="">About Southwestern</a></li>
      <li><a href="">Majors & Minors</a></li>
      <li><a href="">Visit Campus</a></li>
      <li><a href="">Financial Aid</a></li>
      <li><a href="">Apply</a></li>
      <li><a href="">Athletics</a></li>
      <li><a href="">Study Abroad</a></li>
      <li><a href="">Alumni Success Stories</a></li>
      <li><a href="">Registrar & Records</a></li>
      <li><a href="">Student life</a></li>
    </ul>

    <div :class="{ open: menuOpen }" class="nav-content">
    </div>

    <div class="content" style="background-image: url('static/img/bugaboo-spire.jpg')"><!-- home page content --></div>

  </div>
</template>

<script>
import anime from 'animejs';

export default {
  name: 'app',
  data () {
    return {
      menuOpen: false,
      defaultEasing: [0.25, 0.1, 0.25, 1] // from Principle
    }
  },
  mounted: function () {
    // set event handlers here since this will
    // be implemented statically
  },
  methods: {
    toggleMenu: function (e) {
      this.menuOpen = !this.menuOpen;

      this.animateMenu();
    },
    /*
      - NOTE: using vuejs only for the dev environment
      - coded so it easily be transferred to a static page
      ***************************************
      - on menu click open full screen menu
      - 1st level menu items
        - stagger animate to right and fade in
      - first item is selected
      - 2nd level menu
        - stagger animate to right and fade in
      - extra content window
        - animate / fade in grey background
        - show content
    */
    animateMenu: function () {
      // let timelinePrimary = anime.timeline();
      const navContent = document.querySelector('.nav-content');
      const primaryMenu = document.querySelector('.menu-primary');
      const primaryLi = document.querySelectorAll('.menu-primary li');
      const menuLabel = document.querySelector('.menu-label');
      const appWidth = this.$el.clientWidth;
      const appDirection = (this.menuOpen) ? appWidth : -appWidth
      // const dir = (this.menuOpen) ? 'normal' : 'reverse';
      const menuOpacity = (this.menuOpen) ? 1 : 0;
      let navTimeline = anime.timeline();
      // Menu Container
      anime({
        targets: navContent,
        translateX: appDirection,
        easing: this.defaultEasing,
        duration: 650,
        begin: function (anim) {
          setTimeout(function () {
            menuLabel.classList.toggle('opened')
          }, 300)
        }
      })

      navTimeline
        .add({
          targets: primaryMenu,
          opacity: menuOpacity,
          delay: -500
        })
        .add({
          targets: primaryLi,
          translateX: this.menuOpen ? 20 : 0,
          opacity: menuOpacity,
          delay: function (el, i, l) {
            return i * 100;
          }
        })

      // non-timeline version
      // Primary nav
      // anime({
      //   targets: primaryMenu,
      //   direction: dir,
      //   opacity: opa,
      //   delay: 300
      // });

      // Primary nav lis
      // anime({
      //   targets: primaryLi,
      //   translateX: this.menuOpen ? 20 : 0,
      //   opacity: opa,
      //   delay: function (el, i, l) {
      //     return i * 100;
      //   }
      // });
    }
  }
}
</script>

<style lang="sass">
@import './sass/reset'
@import './sass/app'
</style>
