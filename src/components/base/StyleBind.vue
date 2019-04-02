<template>
  <div>
    <div :style="{width:square.width, height:square.height, border:square.border}"></div>
    <div :style="{marginTop:'10px',width:circle.width, height:circle.height, border:circle.border, radius:circle.radius}"></div>
    <div></div>
  </div>
</template>

<script>
export default {
  name: 'StyleBind',
  data () {
    return {
      square: {
        height: '40px',
        width: '40px',
        border: '1px solid black'
      },
      circle: {
        height: '45px',
        width: '45px',
        border: '1px solid red',
        radius: '45px'
      }
    }
  }
}
</script>

<style scoped>

</style>
