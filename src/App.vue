<template>
  <div id="app">
    <svg class="logo" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 270.1 300">
      <path class="st0" d="M127.9 297h-12.7L95 261.6V297H82.2v-60.7H95l20.2 35.5v-35.5h12.7zM169 297h-22.4c-5.6 0-10-4.5-10-10v-40.6c0-5.6 4.5-10 10-10H169c5.6 0 10 4.5 10 10V287c0 5.5-4.5 10-10 10m-4.1-48.7h-14.2c-.5 0-.9.4-.9.9V284c0 .5.4.9.9.9h14.2c.5 0 .9-.4.9-.9v-34.8c0-.5-.4-.9-.9-.9M187.5 236.3h13.2v48.6h19.4V297h-32.6zM267 286.9c0 5.6-4.5 10-10 10h-20.6c-5.6 0-10-4.5-10-10v-8.1h12.9v5.2c0 .5.4.9.9.9H253c.5 0 .9-.4.9-.9v-8.5c0-.6-.5-1-1.2-1.2-1.5-.5-6.4-1.8-17.7-5-5.4-1.5-8.5-3.9-8.5-9.5v-13.6c0-5.6 4.5-10 10-10h20c5.6 0 10 4.5 10 10v8h-12.9v-5.1c0-.5-.4-.9-.9-.9h-12.2c-.5 0-.9.4-.9.9v7.8c0 .7.5 1 1 1.2.9.3 6.1 1.7 18.1 5.1 5.2 1.5 8.2 3.9 8.2 9.5v14.2z"></path>
      <path class="st0" d="M266.9 3H3.2v282.1l116-104.7c.3-.3.8-.3 1.2 0l15.3 14.1c.3.3.8.3 1.2 0l48.1-44c.3-.3.8-.3 1.2 0l80.9 73.7L266.9 3zm-25.5 168.8L186 121.2c-.3-.3-.8-.3-1.2 0L137 165.4c-.3.3-.8.3-1.2 0l-15.5-14.2c-.3-.3-.8-.3-1.2 0l-51.3 46.4C61.6 185.1 58 171 58 156c0-51 41.4-92.4 92.4-92.4 51 0 92.4 41.4 92.4 92.4 0 5.4-.5 10.7-1.4 15.8"></path>
    </svg>

    <label class="menu-label">
      <button @click="toggleMenu" class="button menu-link">
        <svg width="13px" height="10px" viewBox="0 0 13 10" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
            <g class="icon-menu-open" fill-rule="evenodd" stroke-linecap="square">
              <path d="M0,1 L10.9655725,1"></path>
              <path d="M0,5 L8,5"></path>
              <path d="M0,9 L10.9655725,9"></path>
            </g>
            <g class="icon-menu-close" transform="translate(2,1)">
              <path d="M1,0 L9,8"></path>
              <path d="M9,0 L1,8"></path>
            </g>
        </svg>
      </button> <b>Menu</b>
    </label>
    <!-- Do not dynamically create menu. This needs to be
         implemented in a static page -->
    <div class="menus-container">
      <div class="menus">
        <ul class="menu-primary">
          <li><a href="">Becoming a Student</a></li>
          <li><a href="">Current Students</a></li>
          <li><a href="">Parents & Family</a></li>
          <li><a href="">Faculty & Staff</a></li>
          <li><a href="">Alumni</a></li>
        </ul>

        <ul class="menu-secondary">
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
      </div>
      <!-- TODO: make side content wrap -->
      <div class="side-content-wrapper">
        <div class="side-content">
          side content and stuff
        </div>
      </div>
    </div>

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
    const menuLinks = document.querySelectorAll('li a');

    menuLinks.forEach(function (d) {
      d.addEventListener('click', function (e) {
        e.preventDefault();
      })
    })
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
      TODO:
        -
    */
    animateMenu: function () {
      // const vm = this;
      const navContent = document.querySelector('.nav-content');
      const primaryMenu = document.querySelector('.menu-primary');
      const primaryLi = primaryMenu.querySelectorAll('.menu-primary li');
      const firstLink = primaryMenu.querySelector('a');
      const secondaryMenu = document.querySelector('.menu-secondary');
      const secondaryLi = secondaryMenu.querySelectorAll('.menu-secondary li');
      const menuLabel = document.querySelector('.menu-label');
      const sideContent = document.querySelector('.side-content-wrapper');
      const logo = document.querySelector('.logo');
      const menuOpacity = this.menuOpen ? 1 : 0;
      const defaultTiming = 650;

      let navTimeline = anime.timeline({
        autoplay: true
      });
      // Nav container with white background
      anime({
        targets: navContent,
        width: this.menuOpen ? '100%' : 0,
        easing: this.defaultEasing,
        duration: defaultTiming,
        begin: function (anim) {
          // toggle logo color
          setTimeout(function () {
            logo.classList.toggle('opened')
          }, 200)
          // toggle menu icon
          setTimeout(function () {
            menuLabel.classList.toggle('opened')
          }, 250)
          // set first nav li active
          setTimeout(function () {
            firstLink.classList.toggle('active')
          }, 400)
        }
      })
      // NOTE: setting duration on open only
      //       and resetting to 0 on close
      navTimeline
        .add({
          targets: primaryMenu,
          opacity: menuOpacity,
          duration: defaultTiming,
          delay: -500
        })
        .add({
          targets: primaryLi,
          elasticity: 0,
          translateX: this.menuOpen ? 20 : 0,
          opacity: menuOpacity,
          delay: function (el, i, l) {
            return i * 100;
          }
        })
        .add({
          targets: secondaryMenu,
          duration: this.menuOpen ? (defaultTiming * 1.5) : 0,
          opacity: menuOpacity
        })
        .add({
          targets: secondaryLi,
          duration: defaultTiming,
          elasticity: 0,
          translateX: this.menuOpen ? 20 : 0,
          opacity: menuOpacity,
          offset: '-=2000',
          delay: function (el, i, l) {
            return i * 50;
          }
        })
        .add({
          targets: sideContent,
          opacity: menuOpacity,
          duration: defaultTiming,
          offset: '-=2000'
        })
    }
  }
}
</script>

<style lang="sass">
@import './sass/reset'
@import './sass/app'
</style>
