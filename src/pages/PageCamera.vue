<template>
  <q-page class="constrain-more q-pa-md">
    <div class="camera-frame q-pa-md">
      <video v-show="!imageCaptured" ref="video" class="full-width" autoplay/>
      <canvas v-show="imageCaptured" ref="canvas" class="full-width" height="240"></canvas>
    </div>
    <div class="text-center q-pa-md">
      <q-btn round color="grey-10" icon="eva-camera" size="lg" @click="captureImage"/>
      <div class="row justify-center q-ma-md">
        <q-input v-model="post.caption" class="col col-sm-6" label="Caption" dense />
      </div>
      <div class="row justify-center q-ma-md">
        <q-input v-model="post.location" class="col col-sm-6" label="Location" dense>
          <template v-slot:append>
            <q-btn round dense flat icon="eva-navigation-2-outline" />
          </template>
        </q-input>
      </div>
      <div class="row justify-center q-mt-lg">
        <q-btn unelevated rounded color="primary" label="Post Image" />
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import { uid } from 'quasar';
require('md-gum-polyfill');

export default defineComponent({
  name: "PageCamera",
  preFetch() {
    function initCamera() {
      navigator.mediaDevices.getUserMedia({
        video: true
      }).then(stream => {
        this.$refs.video.srcObject = stream;
      })
    }
    initCamera()
  },
  setup() {
    const imageCaptured = false;
  function captureImage() {
      let video = this.$refs.video;
      let canvas = this.$refs.canvas;
      canvas.width = video.getBoundingClientRect().width;
      canvas.height = video.getBoundingClientRect().height;
      let context = canvas.getContext('2d');
      context.drawImage(video, 0, 0, canvas.width, canvas.height);
      imageCaptured = true;
    }
    return {
      post: {
        id: uid(),
        caption: '',
        location: '',
        photo: null,
        date: Date.now()
      },
      captureImage,
      imageCaptured
      
    }
  }
});
</script>

<style lang="sass">
.camera-frame
  border: 2px solid $grey-10
  boder-radius: 10px
</style>
