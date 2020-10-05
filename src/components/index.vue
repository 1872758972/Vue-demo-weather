<template>
  <div class="Outsideframe">
    <div class="top">
      <div class="top1">
        <div class="positioninga"><positioning></positioning></div>
        <div class="weathera"><weather></weather></div>
      </div>
    </div>
    <div class="top2">
      <div class="hourweathera"><hourweather></hourweather></div>
      <div class="qwe">
        <div class="weekweathera"><weekweather></weekweather></div>
        <div class="lifeindexa"><lifeindex></lifeindex></div>
      </div>
      <div class="rainfalla"><rainfall></rainfall></div><br>
      <p class="description">Description</p><br><br>
      <p class="descriptionl">作者：Daphnis 美术：Chloe</p><br><br><br>
    </div>
  </div>
</template>
   
<script>
import positioning from '@/components/positioning'
import weather from '@/components/weather'
import hourweather from '@/components/hourweather'
import weekweather from '@/components/weekweather'
import lifeindex from '@/components/lifeindex'
import rainfall from '@/components/rainfall'


export default {
  name:"index",
  components:{
    positioning,weather,hourweather,weekweather,lifeindex,rainfall
  }
};
</script>

<style scoped>

.Outsideframe{
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;  
}
.top{
  margin:0;
  padding: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(215, 233, 235, 0.993);
}
.top1,.top2{
  margin-left: 120px;
  margin-right: 120px;
}
.top2{
  height: 100%;
}
.positioninga{
  height: 100px;
}
.weathera{
  height: 350px;
}
.hourweathera{
  height: 200px;
  margin-top: 100px;
  background-color:rgb(240, 239, 238);
}
.weekweathera{
  width: 60%;
    height: 400px;
    float: left;
    background-color:rgba(0, 0, 0, 0.055)
}
.lifeindexa{
    width: 39%;
    float: left;
    height: 350px;
}
.qwe{
  margin-top: 50px;
  height: 400px;
}
.rainfalla{
  height: 470px;
  width: 100%;
  margin-top: 50px;
}
.description{
  color: rgb(10, 190, 10);
  margin-left: 600px;
  font-size: 20px;
}
.descriptionl{
    color: rgb(10, 190, 10);
    margin-left: 550px;
}
</style>
