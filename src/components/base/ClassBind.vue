<template>
  <div>
    <!--:class的值是一个对象, 等号左侧是css定义中的类，右侧是data中定义的布尔值，布尔值为true，则渲染这个类-->
    <!--注意，css定义类使用的是kebab-case，但在对象中引用时需使用加上引号,否则报错-->
    <div :class="{squareClass: isSquare, 'yellow-background': isYellow}">小矩形</div>
    <!--class与:class并存-->
    <div class='pink-background' :class="{'circleClass': isCircle}">小圆形</div>
    <!--绑定的数据对象不内联定义在模板里，都写在data中-->
    <div :class="shapeObj">大矩形</div>
    <!--绑定一个返回对象的计算属性-->
    <div :class="computedCssObj">大圆形</div>
    <!--数组语法 ,数组中的值是定义在data中的变量，其变量值对应该的是css中定义的类，-->
    <div :class="[squareBigBigClass, yellowBackgroundClass]">超大矩形</div>
    <!--使用三元表达式, 表达式用中括号包围-->
    <div :class="[isSquare ? 'squareClass' : 'circleClass']">小矩形</div>
  </div>
</template>

<script>
export default {
  name: 'ClassBind',
  data () {
    return {
      isSquare: true,
      isCircle: true,
      isSquareBig: true,
      isCircleBig: false,
      isYellow: true,
      shapeObj: {
        /*
        * 注意：'circle-big'对应的是css定义中的circle-big
        * 写成circleBig, 无法识别此类，而在html文件中则需要写camelCase
        * 写成circle-big, 报语法错误，所以必须加上引号
        * */
        'square-big': true, // circle对应css定义中的circle
        'yellow-background': true // yellowBackground对应css定义中的circle
      },
      squareBigBigClass: 'square-big-big',
      yellowBackgroundClass: 'yellow-background'
    }
  },
  computed: {
    computedCssObj () {
      return { // 返回对象，外加大括号
        'circle-big': this.isSquareBig,
        'pink-background': true
      }
    }
  }
}
</script>

<style scoped>
  .squareClass {
    margin-top: 5px;
    width: 40px;
    height: 40px;
    border: 1px solid black
  }
  .circleClass {
    margin-top: 5px;
    width: 40px;
    height: 40px;
    border: 2px solid black;
    border-radius: 40px;
  }
  .square-big {
    margin-top: 5px;
    width: 60px;
    height: 60px;
    border: 2px solid black
  }
  .square-big-big {
    margin-top: 5px;
    width: 80px;
    height: 80px;
    border: 4px solid black
  }
  .circle-big {
    margin-top: 5px;
    width: 60px;
    height: 60px;
    border: 4px solid black;
    border-radius: 40px;
  }
  .yellow-background {
    background-color: yellow;
  }
  .pink-background {
    background-color: pink;
  }
</style>
