<template>
  <div v-click-outside="hide">
    <div 
      v-random-color-menu
      :class="{ 'active': menuOpen }"
      class="hamburger" 
      @click="toggle"
    >
      <i class="fas fa-bars fa-2x icon-hamburger"/>
      <i class="fas fa-times fa-2x icon-close"/>
    </div>
    <nav 
      :class="{ 'open': menuOpen }"
      class="nav" 
    >
      <ul>
        <li>
          <nuxt-link 
            v-random-color-menu
            to="/"
            @click.native="hide"
          >
            Info
          </nuxt-link>
        </li>
        <li>
          <nuxt-link 
            v-random-color-menu
            to="/projects"
            @click.native="hide"
          >
            Projects
          </nuxt-link>
        </li>
        <li>
          <nuxt-link 
            v-random-color-menu
            to="/personal"
            @click.native="hide"
          >
            Personal Projects
          </nuxt-link>
        </li>
        <li>
          <nuxt-link 
            v-random-color-menu
            to="/technologies"
            @click.native="hide"
          >
            Technologies
          </nuxt-link>
        </li>
        <li>
          <a
            v-random-color-menu
            href="https://console.rubenbielen.com"
          >
            Webapp console (WIP)
          </a>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
import ClickOutside from "vue-click-outside";

export default {
  directives: {
    ClickOutside
  },
  data() {
    return {
      menuOpen: false
    };
  },
  methods: {
    toggle: function() {
      this.menuOpen = !this.menuOpen;
    },
    hide: function() {
      this.menuOpen = false;
    }
  }
};
</script>

