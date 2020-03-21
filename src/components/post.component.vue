<template>
  <div class="col-6 col-sm-3">

  <div class="post" style="margin-bottom: 1.3rem; transition: all .3s ease;">
    <q-card
      class="post__cover cursor-pointer shadow-transition my-hover-shadow w-full"
      @click="goto(item)"
    >
      <q-img
        @mouseenter="isHover = true"
        @mouseleave="isHover = false"
        :src="item.cover"
      >
        <!--          <transition
                    appear
                    enter-active-class="animated slideInDown"
                    leave-active-class="animated slideOutUp"
                  >
                    <div v-if="isHover" class="w-full" style="width: 100%; height: 100%">
                      <div class="absolute-top-right q-ma-sm">
                        <q-btn push color="white" text-color="primary" size="12px" icon="favorite" class="q-mr-md"/>
                        <q-btn push color="white" text-color="primary" size="12px" label="收集" style="width: 90px"
                               @click="onCollection = true"/>
                      </div>
                      <q-btn
                        key="open-in-new"
                        push color="white"
                        text-color="primary"
                        round class="absolute-bottom-right q-ma-sm"
                        icon="open_in_new"
                        @click="goto(item)"
                      />
                    </div>
                  </transition>-->
      </q-img>
    </q-card>
    <div class="q-mt-md">
      <div class="text-h6">{{ item.title }}
        <q-popup-edit
          v-model="item.title"
          :offset="[0, 10]"
          buttons
          label-set="保存" label-cancel="取消"
          :cover="false"
        >
          <q-input
            type="textarea"
            color="black" v-model="item.title" dense autofocus counter>
            <template v-slot:prepend>
              <q-icon name="notes" color="black"/>
            </template>
          </q-input>
        </q-popup-edit>
      </div>
      <div class="text-subtitle2">
        {{ item.content }}
        <q-popup-edit
          v-model="item.content"
          :offset="[0, 10]"
          buttons
          label-set="保存" label-cancel="取消"
          :cover="false"
          @save="onContentSave"
        >
          <q-input
            type="textarea"
            color="black" v-model="item.content" dense autofocus counter>
            <template v-slot:prepend>
              <q-icon name="notes" color="black"/>
            </template>
          </q-input>
        </q-popup-edit>
      </div>
    </div>
  </div>
  </div>

</template>

<script>
export default {
  props: {
    item: {
      type: Object
    }
  },
  methods: {
    onContentSave () {},
    onTitleSave () {},
    goto (item) {
      window.open(item.guid, '_blank')
    }
  }
}
</script>
<style lang="stylus">
  .post
    padding: 10px 15px
    .q-card
      /*width: 100%*/
      /*max-width: 205px*/
      box-shadow none
    &__cover
      border: 1px solid $separator-color
      /*width: 205px*/
      /*height: 205px*/
  /*a
    &::after
      content: "";
      width: 22px;
      height: 9px;
      display: inline-block;
      // background: url(assets/hyperlink.svg) no-repeat;
      background-size: 22px 9px;
      margin-left: 5px;
      position: absolute;
      top: 7px;
      opacity: 0;
      transition: all .2s ease;*/
  .my-hover-shadow:hover
    border: 1px solid $separator-color
    box-shadow $shadow-18

</style>
