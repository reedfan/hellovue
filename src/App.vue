<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对React的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <Add :addComment="addComment"/>
      <!--组件间通信，将值传递过去，最好是重名,如果不加：，传过去的将是vue这个文本，加：传过去的将是变量的值，下一步List接收-->
      <List :comments="comments"/>


    </div>
  </div>

</template>

<script>



  // 1.引入
  import Add from './components/Add'
  import List from './components/List'
export default {

//数组在哪个组件，更新数据的行为（方法）就应该定义在哪个组件

  data (){
    return{
      comments: [
        {
          name: 'reed1',
          content: 'vue 还不错'
        },
        {
          name: 'reed2',
          content: 'vue so easy'
        }

      ]

    }



  },

  methods: {
    //添加评论
    addComment(comment){
      this.comments.unshift(comment)

    },
    //删除指定下标的评论
    deleteComment(index){
      this.comments.splice(index,1)
    }
  },


    //2。标签
    components: {
      Add,
      List
    }

}
</script>

<style>

</style>
