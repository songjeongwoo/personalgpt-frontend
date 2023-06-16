<template>
  <v-app>
    <!-- <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar> -->

    <!-- 사이드바 -->
    <side-bar></side-bar>
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/> -->

    <v-main>
      <!-- <div class="main-content">
        <HelloWorld/>
      </div> -->
      <div class="chat-container">
        <ChatInput/>
      </div>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';
// import HelloWorld from './components/HelloWorld.vue';
import SideBar from './views/SideBar.vue';
import ChatInput from './components/ChatInput.vue';

export default Vue.extend({
  name: 'App',

  components: {
    // HelloWorld,
    SideBar,
    ChatInput
  },

  data: () => ({
    //
  }),
});
</script>
<style>
/* .main-content {
  flex-grow: 1;
  padding: 16px;
  margin-left: 15rem;
} */

.chat-container {
  height: calc(100% - 5rem);
  position: fixed;
  bottom: 0;
  left: 15rem; /* 사이드바 너비 고려 */
  right: 0;
  /* width: calc(100% - 15rem); */
  background-color: white;
  padding: 16px;
  box-shadow: 0px -2px 6px rgba(0, 0, 0, 0.1);
}
</style>
