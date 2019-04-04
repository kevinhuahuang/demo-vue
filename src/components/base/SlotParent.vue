<template>
  <div>
    <SlotChild :shirley="shirley">
      <div>---我是父元素中没有name属性的slot标签，位置：开头---</div>
      <!--slot=one这个div会替换掉子组件里name="kevin"的slot标签-->
        <div slot="kevin">------------------------------------------
          <div>姓名：kevin</div>
          <div>身高: 175cm</div>
          <div>体重：70kg</div>
        </div>
        <!--这个div没有用slot指定名字所以会替换掉子组件里没有name属性的slot标签-->
        <div>
          <span>---我是父元素中没有name属性的slot标签，位置：中间---</span>
        </div>
        <!--slot=two这个div会替换掉子组件里name="vivian"的slot标签-->
        <div slot="vivian">-------------------------------------------
          <div>姓名：vivian</div>
          <div>身高: 165cm</div>
          <div>体重：55kg</div>
        </div>
      <div>---我是父元素中没有name属性的slot标签，位置：结尾---</div>
      <!--父组件所有没有定义slot名的元素全部放在子组件中没有命名的slot里，-->
      <!--如果slot子组件有多个没有名字的slot,它们的内容一样，都包含父组件里所有没有定义slot名的元素-->
      <!--此处slot定义的顺序是kevin,无名，vivian。但其显示顺序是参照子组件的定义顺序-->
    </SlotChild>
  </div>
</template>

<script>
import SlotChild from './SlotChild'
export default {
  name: 'SlotParent',
  components: {SlotChild},
  data () {
    return {
      shirley: {
        name: 'shirley',
        height: '158cm',
        weight: '50kg'
      }
    }
  }
}
</script>

<style scoped>

</style>
