<template>
  <div>
    <div>
      <p>------------------------------------------------------------------------------------</p>
      <p> v-on 指令监听 DOM 事件，并在触发时运行一些 JavaScript 代码, 但使用alert('要显示的数据')时出错</p>
      <button v-on:click="counter += 1">Add 1</button>
      <p>The button above has been clicked {{ counter }} times.</p>
    </div>
    <div>
      <p>------------------------------------------------------------------------------------</p>
      <p> v-on 接收一个需要调用的方法名称</p>
      <button v-on:click="add()">Add 1</button>
      <p>The button above has been clicked {{ counter }} times.</p>
    </div>
    <div>
      <p>------------------------------------------------------------------------------------</p>
      <p> v-on 在内联 JavaScript 语句中调用方法 注意和上面的对比，上面是指向一个方法，这个是调用方法</p>
      <button v-on:click="warn('Form cannot be submitted yet.', $event)">
        Submit
      </button>
    </div>
    <div>
      <p>------------------------------------------------------------------------------------</p>
      <p> 事件修饰符 .stop .prevent .submit .capture .self</p>
      <!--使用修饰符时，顺序很重要；相应的代码会以同样的顺序产生。
      因此，用 v-on:click.prevent.self 会阻止所有的点击，
      而 v-on:click.self.prevent 只会阻止对元素自身的点击。-->
      <!-- 阻止单击事件继续传播 -->
      <a v-on:click.stop="doThis"></a>

      <!-- 提交事件不再重载页面 -->
      <form v-on:submit.prevent="onSubmit"></form>

      <!-- 修饰符可以串联 -->
      <a v-on:click.stop.prevent="doThat"></a>

      <!-- 只有修饰符 -->
      <form v-on:submit.prevent></form>

      <!-- 添加事件监听器时使用事件捕获模式 -->
      <!-- 即元素自身触发的事件先在此处理，然后才交由内部元素进行处理 -->
      <div v-on:click.capture="doThis">...</div>

      <!-- 只当在 event.target 是当前元素自身时触发处理函数 -->
      <!-- 即事件不是从内部元素触发的 -->
      <div v-on:click.self="doThat">...</div>
    </div>
    <div>
      <p>------------------------------------------------------------------------------------</p>
      <p> 按钮码</p>
      <label>在输入框输入空格键，调出消息
        <input v-on:keyup.space="message">
      </label>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Von',
  data () {
    return {
      counter: 1
    }
  },
  methods: {
    add () {
      this.counter += 1
    },
    warn: function (message, event) {
      // 现在我们可以访问原生事件对象
      if (event) event.preventDefault()
      alert(message)
    },
    doThis () {
    },
    doThat () {
    },
    onSubmit () {
    },
    message () {
      alert('你输入了空格键')
    }
  }
}
</script>

<style scoped>

</style>
