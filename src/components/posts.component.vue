<template>
  <q-infinite-scroll @load="onLoad" :offset="250">
    <div class="posts row q-mt-lg">
      <post-component
        :item="item"
        v-for="(item, index) in posts" :key="index"/>
    </div>
    <template v-slot:loading>
      <div class="row justify-center q-my-md">
        <q-spinner-dots color="primary" size="40px" />
      </div>
    </template>
  </q-infinite-scroll>
</template>

<script>
import gql from 'graphql-tag'
import PostComponent from '../components/post.component'
const postQuery = gql`
          query GetPosts($limit: Int, $offset: Int) {
            posts_aggregate{
                aggregate{
                    count
                }
            }
            posts (limit: $limit, offset: $offset) {
                id
                guid
                title
                description
                cover
                content
            }
        }`
export default {
  data () {
    return {
      limit: 50,
      offset: 0,
      posts: [],
      totalItems: 0
    }
  },
  components: {
    PostComponent
  },
  created () {
    this.loadPosts()
  },
  methods: {
    async loadPosts (offset = 0) {
      // const { totalItems, items}
      const res = await this.$apollo.query({
        query: postQuery,
        variables () {
          return {
            limit: this.limit,
            offset: this.offset
          }
        }
      })
      // console.log(res.data.posts_aggregate.aggregate.count)
      this.totalItems = res.data.posts_aggregate.aggregate.count
      // console.log(res.data.posts)
      // this.items = res.data.posts
      this.posts.push(...res.data.posts)
    },
    onLoad (index, done) {
      if (this.posts && this.posts.length > 0 && this.posts.length < this.totalItems) {
        setTimeout(() => {
          this.loadPosts(this.posts.length)
          done()
        }, 500)
      } else {
        done()
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
</style>
