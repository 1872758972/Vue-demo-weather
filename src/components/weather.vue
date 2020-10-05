<template>
  <div class="weather">
      <div class="weather1">
          <p class="p1">中央气象台{{ positiond.update_time }}发布</p><br><br><br>
          <div><p class="p2">{{ positiond.tem}}℃</p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<i class=" iconfont icon-kongqizhiliang">{{ positiond.wea}} &nbsp;&nbsp;{{ positiond.air}}</i></div><br><br><br>
          <p class="p3"><i class=" iconfont icon-feng"></i>&nbsp;&nbsp;{{ positiond.win}} {{ positiond.win_speed}} &nbsp;&nbsp;&nbsp;<i class=" iconfont icon-shuidi"></i>&nbsp;&nbsp;湿度&nbsp;{{ positiond.humidity}}&nbsp;&nbsp;&nbsp;<i class=" iconfont icon-qiya"></i>&nbsp;&nbsp;气压&nbsp;{{ positiond.pressure}}&nbsp;hPa</p>
      </div>
      <div class="day">
          <i class=" iconfont " :class="change==1 ? 'icon-baitian1' : 'icon-wanshang2'"></i>
      </div>
  </div>
</template>

<script>
export default {
    name:'weather',
    data () {
        return {
            positiond:[],
            change:''
        }
    },
    mounted(){
        bus.$on('passvaluea',(value)=>{
            this.positiond=value;
        })
        bus.$on('passvalueb',(value)=>{
            this.change=value;
        })
        
    },
};
</script>

<style>
p,i{
    display: inline;
}
.weather1{
    float: left;
    width: 700px;
}
.day{

    float: left;
    margin-left: 100px;
    margin-top: 100px;
}
.day i{
    font-size: 100px;
    color: rgba(255, 255, 0, 0.664);
}
.p2{
    font-size: 50px;
}
.p3{
    font-size: 20px;
}
.icon-kongqizhiliang{
    font-size:25px
}
</style>