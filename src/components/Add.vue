<template lang="">
    <div class="col-md-4">
        <h3>添加评论</h3>
        用户名：
        <input type="text"  v-model="name"><br/>
        评论内容：
        <input type="text" v-model="content">
        <button @click="add()">提交</button>
    </div>
</template>

<script>
export default {
  props: {
    addComment: {
      type: Function,
      required: true
    }
  },
  data () {
    return {
      name: '',
      content: ''
    }
  },
  methods: {
    add () {
      /*  检查输入的合法性 根据输入的数据封装一个comment对象  添加到comments中  清楚输入 */
      const name = this.name.trim()
      const content = this.content.trim()
      if (!name || !content) {
        alert('不为空')
        return
      }
      const comment = {
        name,
        content
      }
      this.addComment(comment)
      this.name = ''
      this.content = ''
    }
  }
}
</script>

<style lang=""></style>
