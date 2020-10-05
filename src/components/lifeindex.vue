<template>
  <div class="life">
    <div class="life1">
      <el-collapse v-model="activeNames" @change="handleChange">
        <div class="life2">
          <div class="life11"><el-collapse-item title="穿衣指数" name="1">{{indexl[3].desc}}</el-collapse-item></div>
          <div class="life11"><el-collapse-item title="运动指数" name="2">{{indexl[1].desc}}</el-collapse-item></div>
          <div class="life11"><el-collapse-item title="洗车指数" name="3">{{indexl[4].desc}}</el-collapse-item></div>
        </div>
        <div class="life3">
          <div class="life11"><el-collapse-item title="中暑指数" name="4">{{indexl[0].desc}}</el-collapse-item></div>
          <div class="life11"><el-collapse-item title="紫外线指数" name="5">{{indexl[5].desc}}</el-collapse-item></div>
          <div class="life11"><el-collapse-item title="血糖指数" name="6">{{indexl[2].desc}}</el-collapse-item></div>
        </div>
      </el-collapse>
    </div>
  </div>
</template>

<script>
export default {
    name:'lifeindex',
    data () {
        return {
            hover:false,
            indexl:[],
            activeNames: ['1']
        }
    },
    mounted(){
        bus.$on('passvalueab',(value)=>{
            this.indexl=value;
        })
    },
    methods: {
      handleChange(val) {
        console.log(val);
      }
    }
}
</script>

<style>
.life2{
  width: 240px;
  height: 350px;
  float: left;
}
.life3{
  width: 240px;
  height: 350px;
  float: left;
}
.life11{
  margin-left: 50px;
  width: 150px;
  height: 100px;
  margin-top: 25px;
}
</style>