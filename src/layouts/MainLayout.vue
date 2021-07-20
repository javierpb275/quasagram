<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-white text-grey-10" bordered>
      <q-toolbar class="constrain">
        <q-btn class="large-screen-only q-mr-sm" to="/camera" flat round dense size="18px" icon="eva-camera-outline" />
            <q-separator vertical spaced class="large-screen-only"/>
        <q-toolbar-title class="text-grand-hotel text-bold"> 
          Quasagram
        </q-toolbar-title>
        <q-btn class="large-screen-only" to="/" flat round dense size="18px" icon="eva-home-outline" />
      </q-toolbar>
    </q-header>

    <q-footer class="bg-white small-screen-only" bordered>

        <q-tabs class="text-grey-10" active-color="primary" indicator-color="transparent">
          <q-route-tab to="/" name="home" icon="eva-home-outline"/>
          <q-route-tab to="/camera" name="camera" icon="eva-camera-outline"/>
        </q-tabs>

    </q-footer>

    <q-page-container class="bg-grey-1">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "MainLayout",

  setup() {
    return {};
  },
});
</script>

<style lang="sass" >
  .q-toolbar 
    height: 77px
    
  .q-toolbar-title
    font-size: 30px
    text-align: center

  .q-footer
    .q-tab__icon
      font-size: 30px
</style>
