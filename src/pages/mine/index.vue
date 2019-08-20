<template>
  <div class="mine">
    <div class="top">
      <button
        class="get-info"
        type="primary"
        v-if="!userInfo.nickName"
        open-type="getUserInfo"
        @click="getUserInfo"
      > 登录 </button>
      <block v-else>
        <image class="avatar" :src="userInfo.avatarUrl" mode="cover" />
        <span class="name">{{userInfo.nickName}}</span>
        <button class="to-edit" @click="toEdit">编辑资料</button>
      </block>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      content: '个人中心',
      userInfo: mpvue.getStorageSync('userInfo') || {}
    }
  },
  methods: {
    getUserInfo () {
      mpvue.getUserInfo({
        success: (res) => {
          this.userInfo = res.userInfo
          mpvue.setStorageSync('userInfo', this.userInfo)
        }
      })
    },
    toEdit () {
      wx.navigateTo({
        url: '/pages/index/main'
      })
    }
  }
}
</script>

<style scoped>
.mine {
  display: flex;
  flex-direction: column;
}
.mine .top {
  flex-basis: 80px;
  display: flex;
  align-items: center;
}
.top .get-info {
  width: 200px;
  height: 50px;
}
.top .avatar {
  flex-basis: 50px;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: #ccc;
  margin-right: 20px;
}
.top .name {
  flex: 2;
  font-size: 16px;
  color: #333;
}
.top .to-edit {
  flex: 1;
  font-size: 10px;
  color: #999;
  text-align: right;
}
</style>
