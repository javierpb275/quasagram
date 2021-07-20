<template>
  <q-page class="constrain q-pa-md">
    <q-card class="card-post" flat bordered>
      <q-item>
        <q-item-section avatar>
          <q-avatar>
            <img src="https://cdn.quasar.dev/img/boy-avatar.png" />
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label class="text-bold">Pepe</q-item-label>
          <q-item-label caption> San Francisco, United States </q-item-label>
        </q-item-section>
      </q-item>

      <q-separator />

      <q-img src="https://cdn.quasar.dev/img/parallax2.jpg" />

      <q-card-section>
        <div>Golden Gate Bridge</div>
        <div class="text-caption text-grey">July 20 20:07 PM</div>
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "PageHome",
  setup() {
    return {
      posts: [
        {
          id: 1,
          caption: "Golden Gate Bridge",
          date: 1626805041748,
          location: "San Francisco, United States",
          imageUrl: "https://cdn.quasar.dev/img/parallax2.jpg",
        },
        {
          id: 2,
          caption: "Golden Gate Bridge",
          date: 1626805041748,
          location: "San Francisco, United States",
          imageUrl: "https://cdn.quasar.dev/img/parallax2.jpg",
        },
        {
          id: 3,
          caption: "Golden Gate Bridge",
          date: 1626805041748,
          location: "San Francisco, United States",
          imageUrl: "https://cdn.quasar.dev/img/parallax2.jpg",
        },
        {
          id: 4,
          caption: "Golden Gate Bridge",
          date: 1626805041748,
          location: "San Francisco, United States",
          imageUrl: "https://cdn.quasar.dev/img/parallax2.jpg",
        },
      ],
    };
  },
});
</script>

<style lang="sass">
.card-post
  .q-img
    min-height: 200px
</style>