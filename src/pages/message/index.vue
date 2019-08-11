<template>
  <div class="message">
    <span>{{content}}</span>
  </div>
</template>

<script>
export default {
  data () {
    return {
      content: '我的消息'
    }
  }
}
</script>

<style>
.message {
  display: flex;
  flex-direction: column;
}
</style>
