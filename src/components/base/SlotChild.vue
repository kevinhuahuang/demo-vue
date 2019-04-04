<template>
    <div>
      <h3>SlotChild</h3>
      <!--父组件里的定义了或没定义名称的Slot会替换掉SlotChild,所以"我会被父祖件替换掉"是看不见的-->
      <!--如果父组件在使用子组件SlotChild的时候不在里面加内容则这里的slot会显示出来-->
      <slot>我是没有命名的开头slot</slot>
      <slot name="vivian">我会被父祖件替换掉</slot>
      <slot name="kevin">我会被父祖件替换掉</slot>
      <slot>我是没有命名的结尾slot</slot>
      <!--父组件所有没有定义slot名的元素全部放在子组件中没有命名的slot里，-->
      <!--如果slot子组件有多个没有名字的slot,它们的内容一样，都包含父组件里所有没有定义slot名的元素-->
    </div>
</template>

<script>
export default {
  name: 'SlotChild',
  props: ['shirley']
}
</script>

<style scoped>

</style>
