<template>
  <div>
    <h2>提示框</h2>

    <p>
      <vxe-button @click="$XMsg.message({ message: '消息提示' })">消息提示</vxe-button>
      <vxe-button @click="$XMsg.message({ message: '成功消息提示', status: 'success' })">成功消息提示</vxe-button>
      <vxe-button @click="$XMsg.message({ message: '失败消息提示', status: 'error' })">失败消息提示</vxe-button>
      <vxe-button @click="$XMsg.message({ message: '不允许重复点击', id: 'unique1' })">不允许重复点击</vxe-button>
    </p>

    <p>
      <vxe-button @click="$XMsg.alert('基本提示框', '标题1')">基本提示框</vxe-button>
      <vxe-button @click="$XMsg.alert({ message: '成功提示框', status: 'success' })">成功提示框</vxe-button>
      <vxe-button @click="$XMsg.alert({ message: '失败提示框', title: 'app.body.msg.error', status: 'error' })">失败提示框</vxe-button>
      <vxe-button @click="$XMsg.confirm('您确定要删除吗？')">确认提示框</vxe-button>
    </p>

    <p>
      <vxe-button @click="$XMsg.alert({ message: '不要遮罩层', mask: false })">不要遮罩层</vxe-button>
      <vxe-button @click="$XMsg.alert({ message: '不要锁界面', mask: false, lockView: false })">不要锁界面</vxe-button>
    </p>

    <p>
      <vxe-button @click="value1 = !value1">自定义模板</vxe-button>
      <vxe-message v-model="value1">
        <template>
          <p style="color: red">自定义模板</p>
          <p style="color: blue">11111111</p>
          <p style="color: red">2222222222</p>
          <p style="color: blue">333333333</p>
        </template>
      </vxe-message>
    </p>

    <p class="demo-code">{{ $t('app.body.button.showCode') }}</p>

    <pre>
      <code class="html">{{ demoCodes[0] }}</code>
      <code class="javascript">{{ demoCodes[1] }}</code>
    </pre>
  </div>
</template>

<script>
import hljs from 'highlight.js'

export default {
  data  () {
    return {
      value1: false,
      demoCodes: [
        `
        <p>
          <vxe-button @click="$XMsg.message({ message: '消息提示' })">消息提示</vxe-button>
          <vxe-button @click="$XMsg.message({ message: '成功消息提示', status: 'success' })">成功消息提示</vxe-button>
          <vxe-button @click="$XMsg.message({ message: '失败消息提示', status: 'error' })">失败消息提示</vxe-button>
          <vxe-button @click="$XMsg.message({ message: '不允许重复点击', id: 'unique1' })">不允许重复点击</vxe-button>
        </p>

        <p>
          <vxe-button @click="$XMsg.alert('基本提示框', '标题1')">基本提示框</vxe-button>
          <vxe-button @click="$XMsg.alert({ message: '成功提示框', status: 'success' })">成功提示框</vxe-button>
          <vxe-button @click="$XMsg.alert({ message: '失败提示框', title: 'app.body.msg.error', status: 'error' })">失败提示框</vxe-button>
          <vxe-button @click="$XMsg.confirm('您确定要删除吗？')">确认提示框</vxe-button>
        </p>

        <p>
          <vxe-button @click="$XMsg.alert({ message: '不要遮罩层', mask: false })">不要遮罩层</vxe-button>
          <vxe-button @click="$XMsg.alert({ message: '不要锁界面', mask: false, lockView: false })">不要锁界面</vxe-button>
        </p>

        <p>
          <vxe-button @click="value1 = !value1">自定义模板</vxe-button>
          <vxe-message v-model="value1">
            <template>
              <p style="color: red">自定义模板</p>
              <p style="color: blue">11111111</p>
              <p style="color: red">2222222222</p>
              <p style="color: blue">333333333</p>
            </template>
          </vxe-message>
        </p>
        `,
        `
        export default {
          data () {
            return {
              value1: false
            }
          }
        }
        `
      ]
    }
  },
  mounted () {
    Array.from(this.$el.querySelectorAll('pre code')).forEach((block) => {
      hljs.highlightBlock(block)
    })
  }
}
</script>
