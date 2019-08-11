<template>
  <div class="square">
    <span>{{content}}</span>
  </div>
</template>

<script>
export default {
  data () {
    return {
      content: '广场'
    }
  }
}
</script>

<style>
.square {
  display: flex;
  flex-direction: column;
}
</style>
