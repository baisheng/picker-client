<template>
    <q-page class="flex flex-center home-page q-py-lg">

    <!--    <img-->
<!--      alt="Quasar logo"-->
<!--      src="~assets/quasar-logo-full.svg"-->
<!--    >-->
    <posts-component />
  </q-page>
</template>

<script>
import PostsComponent from '../components/posts.component'
export default {
  name: 'PageIndex',
  components: {
    PostsComponent
  }
}
</script>
<style lang="stylus">
  body.body--dark
    background: #fafafa
  .home-page
    font-weight: 300
    max-width: 980px
    margin-left: auto
    margin-right: auto

    .my-card
      width: 400px
      &:hover
        box-shadow: $shadow-2
        transition: $shadow-transition
</style>
