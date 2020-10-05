<template>
  <div class="weekweather">
      <div><p class="pp"><br>&nbsp;&nbsp;&nbsp;7日天气预报</p></div>
      <div class="week">
          <li class="lil" v-for="(usera,index) in weekweathera">
                <p>{{ usera.day.slice(-3,-1) }}</p><br><br>
                <p>{{usera.date.slice(5)}}</p><br><br>
                <p>{{ usera.wea }}</p><br><br>
                <i class=" iconfont " :class="[positioni[index]==0? 'icon-qing' : '']"></i>
                <i class=" iconfont " :class="[positioni[index]==1? 'icon-duoyun' : '']"></i>
                <i class=" iconfont " :class="[positioni[index]==2? 'icon-yintian' : '']"></i>
                <i class=" iconfont " :class="[positioni[index]==3? 'icon-yuyutianxiayuxianxing' : '']"></i><br><br>
                <p>{{ usera.tem1 }}</p><br><br>
                <p>{{ usera.tem2 }}</p><br><br>
                <p class="pw1">{{ usera.win_speed }}</p>
          </li>
      </div>
  </div>
</template>

<script>
export default {
    name:'weekweather',
    data () {
        return {
            weekweathera:[],
            positioni:[]
        }
    },
    mounted () {
        bus.$on('passvaluec',(value)=>{
            this.weekweathera=value;
        })
        bus.$on('passvaluedd',(value)=>{
            this.positioni=value;
        })
    }
}
</script>
<style>
.pw1{
    font-size:1px;
}
.pp{
    font-size: 20px;
}
.week{
    margin-left: 20px;
}
.week i{
    font-size: 50px;
    color: rgba(0, 140, 255, 0.849);
}
.lil{
    margin-left: 5px;
}
</style>
