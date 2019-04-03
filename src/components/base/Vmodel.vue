<template>
  <div>
    <div>
      <p> 文本 input </p>
      <input v-model="message" placeholder="edit me">
      <p>Message is: {{ message }}</p>
    </div>
    <div>
      <p>------------------------------------------------------------------------------------</p>
      <p> 多行文本  textarea </p>
      <span>Multiline message is:</span>
      <p style="white-space: pre-line;">{{ messages }}</p>
      <br>
      <textarea v-model="messages" placeholder="add multiple lines"></textarea>
    </div>
    <div>
      <p>------------------------------------------------------------------------------------</p>
      <p> 复选框  checkbox </p>
      <p>v-model的值是一个数组,元素由被选中的checkbox设置的value组成</p>
      <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
      <label for="jack">Jack</label>
      <input type="checkbox" id="john" value="John" v-model="checkedNames">
      <label for="john">John</label>
      <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
      <label for="mike">Mike</label>
      <br>
      <span>Checked names: {{ checkedNames }}</span>
    </div>
    <div>
      <p>------------------------------------------------------------------------------------</p>
      <p> 单选按钮  radio </p>
      <p>v-model的值对应被选中的checkbox设置的value值</p>
      <input type="radio" id="one" value="One" v-model="picked">
      <label for="one">One</label>
      <br>
      <input type="radio" id="two" value="Two" v-model="picked">
      <label for="two">Two</label>
      <br>
      <span>Picked: {{ picked }}</span>
    </div>
    <div>
      <p>------------------------------------------------------------------------------------</p>
      <p> 选择框  单选时</p>
      <select v-model="selected">
        <option disabled value="">请选择</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
      </select>
      <span>Selected: {{ selected }}</span>
    </div>
    <div>
      <p>------------------------------------------------------------------------------------</p>
      <p> 选择框  多选时(绑定到一个数组) </p>
      <select v-model="selectedMul" multiple>
        <option disabled value="">请选择</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
      </select>
      <span>Selected: {{ selectedMul }}</span>
    </div>
    <div>
      <p>------------------------------------------------------------------------------------</p>
      <p> 选择框  + v-for </p>
      <select v-model="selectedFor">
        <option v-for="option in options" v-bind:value="option.value" :key="option.text">
          {{ option.text }}
        </option>
      </select>
      <span>Selected: {{ selectedFor }}</span>
    </div>
    <div>
      <p>------------------------------------------------------------------------------------</p>
      <p> 值绑定 </p>
      <p> 把值绑定到 Vue 实例的一个动态属性上，这时可以用 v-bind 实现，并且这个属性的值可以不是字符串。 </p>
      <p>复选框</p>
      <input type="checkbox" v-model="toggleValue" true-value="yes" false-value="no">
      <p>绑定的值:{{toggleValue}}</p>
      <p>单选按钮</p>
      <input type="radio" v-model="pickValue" v-bind:value="radioValue">
      <p>绑定的值:{{pickValue}}</p>
      <p>选择框的选项</p>
      <select v-model="selectedValue">
        <!-- 内联对象字面量 -->
        <option v-bind:value="{ number: 123 }">123</option>
      </select>
      <p>绑定的值:{{selectedValue}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Vmodel',
  data () {
    return {
      message: '',
      messages: '',
      picked: '',
      checkedNames: [],
      selected: '',
      selectedMul: [],
      selectedFor: '',
      options: [
        { text: 'One', value: 'A' },
        { text: 'Two', value: 'B' },
        { text: 'Three', value: 'C' }
      ],
      toggleValue: '',
      pickValue: '',
      radioValue: '我是单选按钮1号',
      selectedValue: ''
    }
  }
}
</script>

<style scoped>

</style>
