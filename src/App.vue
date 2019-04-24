<template lang="">
    <div>
        <div class="container row">
          <h1>评论列表---增删</h1>
          <Add :addComment="addComment"/>
          <List :comments="comments" :deleteComment="deleteComment"/>
        </div>
    </div>
</template>

<script>
import Add from './components/Add.vue'
import List from './components/List.vue'

export default {
  data () {
    return {
      comments: [
        {
          'name': 'bob',
          'content': 'Vue ddd'
        },
        {
          'name': 'cat',
          'content': 'Vue aaa'
        },
        {
          'name': 'eee',
          'content': 'Vue ccc'
        }
      ]
    }
  },
  methods: {
    /*  添加评论  */
    addComment (comment) {
      this.comments.unshift(comment)
    },
    /* 删除指定评论下标的评论 */
    deleteComment (index) {
      this.comments.splice(index, 1)
    }
  },
  components: {
    Add,
    List
  }
}
</script>

<style lang=""></style>
