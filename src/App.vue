<template>
  <hello @countupdate="countupdate"/>
  {{count}}
  <hr>
  <world/>
</template>

<script>
import hello from './components/hello.vue'
import world from './components/world.vue'
export default {
  name: 'App',
  components:{
    hello,
    world
  },
  data(){
    return {
      count:0
    }
  },
  methods:{
    countupdate(value){
      this.count=value
    }
  }
}
</script>
