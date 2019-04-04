<template>
  <div>
    <!--第一个slot原来使用的是:name，但不能传数据，因为对象已经占用了name这个属性，不能再用name，所有改为nickName-->
    <slot :alinaNickName="alina.nickName"></slot> <!--数据name将传送给父组件-->
    <slot :alinaHeight="alina.height"></slot>
    <slot :alinaWeight="alina.weight"></slot>
    <!--父组件的数据再传回给父组件-->
    <slot :shirleyNickName="shirley.nickName"></slot> <!--数据name将传送给父组件-->
    <slot :shirleyHeight="shirley.height"></slot>
    <slot :shirleyWeight="shirley.weight"></slot>
  </div>
</template>

<script>
export default {
  name: 'SlotChildScope',
  data () {
    return {
      alina: {
        nickName: 'alina',
        height: '175cm',
        weight: '60kg'
      }
    }
  },
  props: ['shirley']
}
</script>

<style scoped>

</style>
