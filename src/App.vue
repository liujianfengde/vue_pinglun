<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对Vue的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <Add :addComment="addComment"/>
      <List :comments="comments" :deleteComment="deleteComment"/>
    </div>
  </div>
</template>
<script>
  import Add from './components/Add.vue'
  import List from './components/List.vue'
  export default{
    data () {
      return {
        comments:[//数据在那个组件，更新数据的行为就定义在那个组件
          {
            name:'BOB',
            content:'vue 还不错'
          },
          {
            name:'Cat',
            content:'vue 还不错1'
          },
          {
            name:'Banner',
            content:'vue 还不错2'
          }
        ]
      }
    },
    methods:{
      addComment(comment){
        this.comments.unshift(comment)
      },
      deleteComment(index){
        this.comments.splice(index,1)
      }
    },
    components:{
      Add,
      List
    }
  }

</script>
<style>

</style>
