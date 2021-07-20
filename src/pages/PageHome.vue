<template>
  <q-page class="constrain q-pa-md">
    <q-card v-for="post in posts" :key="post.id" class="card-post q-mb-md" flat bordered>
      <q-item>
        <q-item-section avatar>
          <q-avatar>
            <img src="https://cdn.quasar.dev/img/boy-avatar.png" />
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label class="text-bold">Pepe</q-item-label>
          <q-item-label caption> {{post.location}} </q-item-label>
        </q-item-section>
      </q-item>

      <q-separator />

      <q-img :src="post.imageUrl" />

      <q-card-section>
        <div>{{post.caption}}</div>
        <div class="text-caption text-grey">{{niceDate(post.date)}}</div>
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import { date } from 'quasar';

export default defineComponent({
  name: "PageHome",
  setup() {
    function niceDate(value) {
        return date.formatDate(value, 'MMMM D h:mmA')
      };
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
      niceDate
    };
  },
});
</script>

<style lang="sass">
.card-post
  .q-img
    min-height: 200px
</style>