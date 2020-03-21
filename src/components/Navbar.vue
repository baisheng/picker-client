<template>
  <div
    class="transparent fixed fixed-top">

    <q-toolbar class="q-py-sm q-px-md">
      <q-btn  dense flat  size="19px" color="primary" class="q-mr-sm" label="Picker">
        <q-badge transparent align="middle" color="black" class="q-ml-xs">
          beta
        </q-badge>
<!--      <q-menu-->
<!--        anchor="center middle"-->
<!--        self="center middle"-->
<!--      >-->
<!--        <q-list style="min-width: 240px">-->
<!--          <q-item clickable v-close-popup>-->
<!--            <q-item-section>采撷科技</q-item-section>-->
<!--          </q-item>-->
<!--          <q-item clickable v-close-popup>-->
<!--            <q-item-section></q-item-section>-->
<!--          </q-item>-->
<!--        </q-list>-->
<!--      </q-menu>-->
    </q-btn>
<!--    /-->
<!--    <q-btn flat color="primary">-->
<!--      资源-->
<!--      <q-badge transparent align="middle" color="black" class="q-ml-xs">-->
<!--        beta-->
<!--      </q-badge>-->
<!--    </q-btn>-->
      <q-space />
      <div class="q-pl-sm q-gutter-sm row items-center no-wrap">
<!--        <q-btn flat text-color="primary">Blog</q-btn>-->
        <q-btn flat text-color="primary" type="a" href="https://caixie.top" target="__blank">Caixie</q-btn>
<!--        <q-btn outline text-color="black" @click="add">-->
<!--          提交你的工具-->
<!--        </q-btn>-->
      </div>
    </q-toolbar>
  </div>
</template>

<script>
// import Vue from 'vue'
// import { fabGithub } from '@quasar/extras/fontawesome-v5'

// const stringOptions = [
//   'quasarframework/quasar',
//   'quasarframework/quasar-awesome'
// ]
export default {
  name: 'navbar',
  data () {
    return {
      // fabGithub,
      leftDrawerOpen: false,
      showAddDialog: false,
      text: '',
      options: null,
      filteredOptions: []
    }
  },
  methods: {
    add () {
      this.$router.push('create')
      // this.$emit('create:post')
      // this.showAddDialog = true
    }
    // filter (val: any, update: any) {
    //   if (this.options === null) {
    //     // load data
    //     // setTimeout(() => {
    //     //   this.options = stringOptions
    //     //   this.$refs.search.filter('')
    //     // }, 2000)
    //     update()
    //     return
    //   }
    //   if (val === '') {
    //     update(() => {
    //       // this.filteredOptions = this.options.map(op => ({ label: op }))
    //     })
    //     return
    //   }
    //   update(() => {
    //     // this.filteredOptions = [
    //     //   {
    //     //     label: val,
    //     //     type: 'In this repository'
    //     //   },
    //     //   {
    //     //     label: val,
    //     //     type: 'All GitHub'
    //     //   },
    //     //   ...this.options
    //     //     .filter(op => op.toLowerCase().includes(val.toLowerCase()))
    //     //     .map(op => ({ label: op }))
    //     // ]
    //   })
    // }
  }
}
</script>
