<template>
  <div>
    <!--使用了slot-scope，所有的未命名且没有对应数据显示的slot将不显示？-->
      <!--在父级中，具有特殊属性 scope 的 <template> 元素必须存在，表示它是作用域插槽的模板。-->
      <!--scope 的值对应一个临时变量名，此变量接收从子组件中传递的 props 对象.-->
    <!--父组件模板的所有东西都会在父级作用域内编译；子组件模板的所有东西都会在子级作用域内编译-->
      <SlotChildScope :shirley="shirley"> <!--传递数据给子组件-->
        <!--从子组件传过来的名为data值为todo的数据将会被slot-scope接收，需要注意的是，slot-scope接收的是一个对象，-->
        <!--这里命名为slotProps，也就是说你传过来的data将会作为slotProps的一个属性，所以需要slotProps.data才能调用到data-->
        <template slot-scope="message"> <!--元素的显示顺序参照子组件非父组件-->
          <span>{{ message.shirleyNickName }}</span>
          <span>{{ message.shirleyHeight }}</span>
          <span>{{ message.shirleyWeight }}</span>
          <span>{{ message.alinaNickName }}</span>
          <span>{{ message.alinaHeight }}</span>
          <span>{{ message.alinaWeight }}</span>
        </template>
      </SlotChildScope>
  </div>
</template>

<script>
import SlotChildScope from './SlotChildScope'
export default {
  name: 'SlotParentScope',
  components: {SlotChildScope},
  data () {
    return {
      shirley: {
        nickName: 'shirley',
        height: '158cm',
        weight: '50kg'
      }
    }
  }
}
</script>

<style scoped>

</style>
