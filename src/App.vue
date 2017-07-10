<template>
  <div id="app" :class="{ open: menuOpen }">
    <svg class="logo" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 270.1 300">
      <path class="st0" d="M127.9 297h-12.7L95 261.6V297H82.2v-60.7H95l20.2 35.5v-35.5h12.7zM169 297h-22.4c-5.6 0-10-4.5-10-10v-40.6c0-5.6 4.5-10 10-10H169c5.6 0 10 4.5 10 10V287c0 5.5-4.5 10-10 10m-4.1-48.7h-14.2c-.5 0-.9.4-.9.9V284c0 .5.4.9.9.9h14.2c.5 0 .9-.4.9-.9v-34.8c0-.5-.4-.9-.9-.9M187.5 236.3h13.2v48.6h19.4V297h-32.6zM267 286.9c0 5.6-4.5 10-10 10h-20.6c-5.6 0-10-4.5-10-10v-8.1h12.9v5.2c0 .5.4.9.9.9H253c.5 0 .9-.4.9-.9v-8.5c0-.6-.5-1-1.2-1.2-1.5-.5-6.4-1.8-17.7-5-5.4-1.5-8.5-3.9-8.5-9.5v-13.6c0-5.6 4.5-10 10-10h20c5.6 0 10 4.5 10 10v8h-12.9v-5.1c0-.5-.4-.9-.9-.9h-12.2c-.5 0-.9.4-.9.9v7.8c0 .7.5 1 1 1.2.9.3 6.1 1.7 18.1 5.1 5.2 1.5 8.2 3.9 8.2 9.5v14.2z"></path>
      <path class="st0" d="M266.9 3H3.2v282.1l116-104.7c.3-.3.8-.3 1.2 0l15.3 14.1c.3.3.8.3 1.2 0l48.1-44c.3-.3.8-.3 1.2 0l80.9 73.7L266.9 3zm-25.5 168.8L186 121.2c-.3-.3-.8-.3-1.2 0L137 165.4c-.3.3-.8.3-1.2 0l-15.5-14.2c-.3-.3-.8-.3-1.2 0l-51.3 46.4C61.6 185.1 58 171 58 156c0-51 41.4-92.4 92.4-92.4 51 0 92.4 41.4 92.4 92.4 0 5.4-.5 10.7-1.4 15.8"></path>
    </svg>

    <label class="menu-label">
      <button @click="toggleMenu" role="button" aria-label="toggle menu" class="button menu-link">
        <svg width="13px" height="10px" viewBox="0 0 13 10" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
            <g class="icon-menu-open" fill-rule="evenodd" stroke-linecap="square">
              <path class="icon-menu-1" d="M0,1 L10.9655725,1"></path>
              <path class="icon-menu-2" d="M0,5 L8,5"></path>
              <path class="icon-menu-3" d="M0,9 L10.9655725,9"></path>
            </g>
        </svg>
      </button> <b>Menu</b>
    </label>

    <div class="header"></div>
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
          <li><a href="">About NOLS</a></li>
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

      <div class="side-content-wrapper">
        <div class="side-content">

          <div class="card">
            <img src="static/img/side-forbes.png" alt="">
            <small class="card-subtitle">ABOUT NOLS</small>
            <h2 class="title">FORBES</h2>
            <p class="info">Forbes names NOLS as the #1 outdoor education school in its 2016 Grateful Grad Colleges. NOLS is also recognized as one of Forbes’ top 50 colleges in the South.</p>
          </div>

          <div class="card">
            <img src="static/img/side-jacobswell.png" alt="">
            <small class="card-subtitle">ATHLETICS</small>
            <h2 class="title">Jacob's Well Diving</h2>
            <p class="info">NOLS men's swimming finishes second, women third at SCAC Championships. Mickey Scharbrough captured the 200-yard breaststroke with a time of 2:06.42, while Belaineh also finished third in the 100-yard fr...</p>
          </div>

          <div class="card">
            <img src="static/img/side-mtadams.png" alt="">
            <small class="card-subtitle">ACADEMICS</small>
            <h2 class="title">School of Mountaineering</h2>
            <p class="info">The School of Mountaineering at NOLS University offers a world-class arts education to our students, and serves the Central Texas community by offering a wide selection of events, each year, in performance and visual arts.</p>
          </div>

          <div class="card">
            <img src="static/img/side-devilsriver.png" alt="">
            <small class="card-subtitle">STUDENT LIFE</small>
            <h2 class="title">Devils River Expedition</h2>
            <p class="info">Devils River is a 4-day paddling and camping festival at NOLS University. Past performers include: Sleigh Bells, Matt & Kim, Del the Funky Homosapien, Black Joe Lewis and the Honeybears and more.</p>
          </div>

          <div class="card">
            <img src="static/img/side-shuksan.png" alt="">
            <small class="card-subtitle">NEW SKILLS</small>
            <h2 class="title">Mount Shuksan Expedtion</h2>
            <p class="info">Mount Shuksan is a 4-day paddling and camping festival at NOLS University. Past performers include: Sleigh Bells, Matt & Kim, Del the Funky Homosapien, Black Joe Lewis and the Honeybears and more.</p>
          </div>

        </div>
      </div> <!-- END .side-content-wrapper -->
    </div>

    <!-- white background that's animated -->
    <div class="nav-content"></div>

    <div class="content" style="background-image: url('static/img/bugaboo-spire.jpg')">
      <!-- homepage content -->
      <div class="tagline">
        <h1>Foster the Next Generation. Give Today to Reach Tomorrow.</h1>
        <button class="button-donate">DONATE TO NOLS</button>
      </div>
    </div>

    <a class="github-icon" href="https://github.com/PaddyMurphy/handsome" title="view on github">
      <b class="show-accessible">view on github</b>
      <svg aria-hidden="true" class="octicon octicon-mark-github" height="24" version="1.1" viewBox="0 0 16 16" width="24"><path fillRule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0 0 16 8c0-4.42-3.58-8-8-8z" /></svg>
    </a>

  </div>
</template>

<script>
import anime from 'animejs';

let navContent, menuLinks, primaryMenu, primaryLi, firstLink, secondaryMenu, secondaryLi, menuLabel, button, sideContent, logo, cards;

const defaultTiming = 650;
// from Principle
const defaultEasing = [0.25, 0.1, 0.25, 1];

export default {
  name: 'app',
  data () {
    return {
      menuOpen: false
    }
  },
  mounted: function () {
    // set event handlers here since this will
    // be implemented statically

    // set selectors once
    navContent = document.querySelector('.nav-content');
    primaryMenu = document.querySelector('.menu-primary');
    primaryLi = primaryMenu.querySelectorAll('li');
    firstLink = primaryMenu.querySelector('a');
    secondaryMenu = document.querySelector('.menu-secondary');
    secondaryLi = secondaryMenu.querySelectorAll('li');
    menuLabel = document.querySelector('.menu-label');
    button = menuLabel.querySelector('.button');
    sideContent = document.querySelector('.side-content-wrapper');
    logo = document.querySelector('.logo');
    cards = document.querySelectorAll('.card');

    menuLinks = document.querySelectorAll('li a');

    menuLinks.forEach(function (d) {
      d.addEventListener('click', function (e) {
        e.preventDefault();
      })
    })
  },
  methods: {
    toggleMenu: function (e) {
      this.menuOpen = !this.menuOpen;
      // disable clicking quickly
      e.target.disabled = true;
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
      const menuOpacity = this.menuOpen ? 1 : 0;

      let navTimeline = anime.timeline({
        autoplay: true
      });
      // Nav container with white background
      anime({
        targets: navContent,
        width: this.menuOpen ? '100%' : 0,
        easing: defaultEasing,
        duration: defaultTiming,
        begin: function (anim) {
          // toggle logo color
          setTimeout(function () {
            logo.classList.toggle('open')
          }, 200)
          // toggle menu icon
          setTimeout(function () {
            menuLabel.classList.toggle('open')
          }, 100)
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
          },
          complete: function () {
            // reenable menu button
            button.disabled = false;
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
          translateX: this.menuOpen ? 40 : 0,
          opacity: menuOpacity,
          offset: '-=2000',
          delay: function (el, i, l) {
            return i * 70;
          }
        })
        .add({
          targets: sideContent,
          opacity: menuOpacity,
          width: this.menuOpen ? '100%' : 0,
          duration: defaultTiming,
          offset: '-=2000'
        })
        .add({
          targets: cards,
          elasticity: 0,
          opacity: menuOpacity,
          duration: 1500,
          offset: '-=1500',
          translateX: this.menuOpen ? 20 : 0,
          delay: function (el, i, l) {
            return i * 150;
          }
        })
    }
  }
}
</script>

<style lang="sass">
@import url('//fonts.googleapis.com/css?family=Playfair+Display:900');
@import './sass/reset'
@import './sass/app'
@import './sass/sidecontent'
</style>
