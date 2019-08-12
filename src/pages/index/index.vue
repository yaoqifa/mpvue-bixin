<template>
  <div class="index page-ontainer" @click="clickHandle">
    <div class="list">
      <card v-for="item in list" :info="item" :key="item.id"></card>
    </div>
  </div>
</template>

<script>
import card from '@/components/card'

export default {
  data () {
    return {
      list: [
        {
          id: 10001,
          name: 'Carol',
          certifyStatus: false,
          introLength: 30,
          sex: 'male',
          address: '上海',
          age: '93年',
          school: '上海大学',
          url: '/static/images/user.png'
        },
        {
          id: 10002,
          name: '我的名字',
          certifyStatus: false,
          introLength: 120,
          sex: 'female',
          address: '上海',
          age: '93年',
          school: '上海大学',
          url: '/static/images/face.jpg'
        }
      ]
    }
  },

  components: {
    card
  },

  methods: {
    clickHandle (ev) {
      console.log('clickHandle:', ev)
      // throw {message: 'custom test'}
    }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style scoped>
.page-ontainer {
  background: #eee;
  min-height: 100%;
  overflow: scroll;
}

</style>
