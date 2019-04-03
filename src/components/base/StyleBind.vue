<template>
  <div>
    <h1 style="text-align: left">绑定内联样式</h1>
    <!---style与:style 可共存的-->
    <!--在绑定的内联样式对象里，margin-top要写成marginTop或者'margin-top'(带引号)-->
    <div style="width:160px; height:40px; border: 2px solid red;" :style="{marginTop: marginTopValue}">普通模式 + 内联样式</div>
    <!--把样式写在对象里，调用方式1-->
    <div :style="{width:square.width, height:square.height, border:square.border,'margin-top':marginTopValue,}">样式写在对象1</div>
    <!--把样式写在对象里，调用方式2-->
    <div :style="circle">样子写在对象2</div>
    <!--数组语法 数组中的元素是对象，对象的内容是单个或多个style的键值对-->
    <div :style="[marginTopStyle, square]">数组语法</div>
    <!--多个值的数组，常用于提供多个带前缀的值-->
    <div :style="{ display: ['-webkit-box', '-ms-flexbox', 'flex'] }"></div>
    <!---->
    <div></div>
  </div>
</template>

<script>
export default {
  name: 'StyleBind',
  data () {
    return {
      marginTopValue: '30px',
      marginTopStyle: {
        marginTop: '10px'
      },
      square: {
        height: '40px',
        width: '200px',
        border: '1px solid black'
      },
      circle: {
        'margin-top': '10px', // 'margin-top'也可以写成marginTop
        height: '80px',
        width: '80px',
        border: '5px solid red',
        'border-radius': '80px'
      }
    }
  }
}
</script>

<style scoped>

</style>
