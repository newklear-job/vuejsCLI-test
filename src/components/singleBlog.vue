<template>
  <div id="single-blog">
      <h1>{{blog.title}}</h1>
      <article>
          {{blog.content}}
      </article>
      <p>Author {{blog.author}}</p>
      <ul>
        <li v-for="category in blog.categories">{{category}}</li>
      </ul>
  </div>
</template>

<script>
  export default{
    data(){
      return {
          id: this.$route.params.id,
          blog: {}
      }
    },
    created(){
      var get_string = 'https://vuejscli-test.firebaseio.com/posts/' + this.id + '.json'
      console.log(get_string)
      this.$http.get(get_string).then(function(data){
          return data.json();
      }).then(function(data){
          this.blog = data;
      });
    }
  }
</script>
<style scoped>
#single-blog{
  max-width:960px;
  margin: 0 auto;
}
</style>
