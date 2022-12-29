<template>
  <PCWeb v-if="!PhoneWebMode" />
  <PhoneWeb v-if="PhoneWebMode"/>
</template>

<script>
import PCWeb from "@/components/PCWeb";
import PhoneWeb from "@/components/PhoneWeb";

export default {
  name: 'App',
  components: {
    // eslint-disable-next-line vue/no-unused-components
    PCWeb, PhoneWeb
  },
  data() {
    return{
      PhoneWebMode : true,//是否为手机模式
      webH: 0,//网页高度
      webW: 0,//网页宽度
    }
  },
  created() {
    this.webW = window.innerWidth
    this.webH = window.innerHeight
    console.log(this.webW, this.webH)
    if(this.webW > this.webH){this.PhoneWebMode = false}
  },
  methods: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
