<template>
  <div class="mine">
    <span>{{content}}</span>
  </div>
</template>

<script>
export default {
  data () {
    return {
      content: '个人中心'
    }
  }
}
</script>

<style>
.mine {
  display: flex;
  flex-direction: column;
}
</style>
