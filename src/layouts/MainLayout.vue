<template>
  <q-layout class="" style="background: #fafafa;">
    <top-bar @create:post="toggleModal"/>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
// import Vue from 'vue'
import TopBar from '../components/Navbar.vue'
export default {
  name: 'MyLayout',
  components: {
    TopBar
  },
  data () {
    return {
      loadingState: false,
      leftDrawerOpen: false,
      isPostModal: false,
      step: 1,
      url: '',
      autoCapture: false,
      item: {
        cover: 'images/illustration/doodles.png',
        guid: 'https://www.opendoodles.com/',
        description: '涂鸦类型的插画集',
        title: 'Open Doodles',
        content: '来自墨西哥设计师 Pablo Stanley 的最新免费插画资源，你可以出于任何目的复制、编辑、重组、共享或重画这些图像，同时完全不必担心版权的限制。'
      }
    }
  },
  methods: {
    toggleModal () {
      this.isPostModal = !this.isPostModal
    },
    onCheck () {
      this.loadingState = !this.loadingState
    }
  }
}
</script>
