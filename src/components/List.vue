<template lang="">
    <div class="col-md-8">
        <h2 v-show="comments.length===0">暂无评论</h2>
        <h3>评论列表</h3>
        <ul>
            <Item v-for="(comment,index) in comments" :key="index" :comment="comment" :deleteComment="deleteComment" :index="index"/>
        </ul>
    </div>
</template>

<script>
import Item from './Item.vue'

export default {
/* 声明接受属性,这个属性就会成为组件对象的属性  只制定属性名 */
  props: ['comments', 'deleteComment'],
  components: {
    Item
  }
}
</script>

<style lang=""></style>
