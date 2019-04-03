<template>
  <div>
    <p>------------------------------------------------------------------------------------</p>
    <p> 数组 (v-for中的in可以用of替代)</p>
    <ul>
      <!-- 可以用of 代替 in -->
      <li v-for="(item, index) in menuArray" v-bind:key="index">
        {{ item }}
      </li>
    </ul>
    <p>------------------------------------------------------------------------------------</p>
    <p> 对象 </p>
    <ul>
      <!-- 三个参数分别为 键值 键名 索引 -->
      <li v-for="(value, key , index) in menuObj" v-bind:key="key">
       {{index}}.{{key}} : {{ value }}
      </li>
    </ul>
    <p>------------------------------------------------------------------------------------</p>
    <p> 一段取值范围的v-for </p>
    <ul>
      <!-- 三个参数分别为 键值 键名 索引 -->
      <li v-for="n in 10" v-bind:key="n">
       {{n}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Vfor',
  data () {
    return {
      menuArray: ['白切鸡', '烤乳猪', '蜜汁叉烧', '脆皮烧肉', '支竹羊腩煲', '鱼头豆腐汤', '干炒牛河', '清蒸东星斑'],
      menuObj: {
        '客家菜': '客家酿豆腐',
        '潮州菜': '潮汕牛肉火锅',
        '广府菜': '红烧乳鸽'
      }
    }
  }
}
</script>

<style scoped>
  li {
    text-align: left;
  }
</style>
