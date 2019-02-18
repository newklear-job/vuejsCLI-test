<template>
  <div>
    <app-header v-bind:title="title" v-on:changeTitle="updateTitle($event)"></app-header>
    <h1 style="text-align:center">{{title}} - root title</h1>
    <app-ninjas v-bind:ninjas='ninjas'></app-ninjas>
    <button v-on:click="changeTitleLocal">Change Title Local</button>
    <app-footer v-bind:title="title"></app-footer>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Ninjas from './components/Ninjas.vue'

export default {
  components:{
    'app-header': Header,
    'app-footer': Footer,
    'app-ninjas': Ninjas
  },
  data(){
    return {
      ninjas: [
          {name: 'Ryu', speciality: 'Vue Components', show: false},
          {name: 'Crystal', speciality: 'HTML Wizardry', show: false},
          {name: 'Hitoshi', speciality: 'Click Events', show: false},
          {name: 'Tango', speciality: 'Conditionals', show: false},
          {name: 'Kami', speciality: 'Webpack', show: false},
          {name: 'Yoshi', speciality: 'Data Diggin', show: false}
      ],
      title: "Vue Ninjas"
    }
  },
  methods:{
    updateTitle:function(updatedTitle){
        this.title=updatedTitle;
    },
    changeTitleLocal:function(){
      this.title = "WTF IT WORKED";
    }
  }
}
</script>

<style>

</style>
