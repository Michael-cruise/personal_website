<template>
  <div>
    <div style="display: flex;width: 100%;flex-wrap: wrap">
      <LeftUp/>
      <MiddleUp/>
      <RightUp/>
      <LeftCenter/>
      <MiddleCenter/>
      <RightCenter/>
      <LeftDown/>
      <MiddleDown/>
      <RightDown/>
    </div>
  </div>
</template>

<script>
import LeftUp from "@/components/PC/LeftComponent/LeftUp";
import MiddleUp from "@/components/PC/MiddleComponent/MiddleUp";
import RightUp from "@/components/PC/RightComponent/RightUp";
import LeftCenter from "@/components/PC/LeftComponent/LeftCenter";
import MiddleCenter from "@/components/PC/MiddleComponent/MiddleCenter";
import RightCenter from "@/components/PC/RightComponent/RightCenter";
import LeftDown from "@/components/PC/LeftComponent/LeftDown";
import MiddleDown from "@/components/PC/MiddleComponent/MiddleDown";
import RightDown from "@/components/PC/RightComponent/RightDown";
import axios from "axios";
export default {
  name: "PCWeb",
  components: {
    // eslint-disable-next-line vue/no-unused-components
    LeftUp,LeftCenter, LeftDown, MiddleUp, MiddleCenter, MiddleDown, RightUp, RightCenter, RightDown,
  },
  mounted() {
    this.getData();
  },
  methods: {
    getData() {
      axios.get("https://devapi.qweather.com/v7/weather/3d?location=121.3,31.15&key=3433aa0d8fbd40f0b3f592e979b148d5")
          .then(resp => {
            console.log(resp );
            //转为jquery对象
          })
      console.log(1)
    }
  }
}
</script>


<style scoped>

</style>