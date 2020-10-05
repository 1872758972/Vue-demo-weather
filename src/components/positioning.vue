<template>
  <div class="positioning">
      <h2>Weather of Daphnis&Chloe</h2>
      <div class="input">
        <i class="el-icon-location-outline"></i>
        &nbsp;
        {{ position }}&nbsp;&nbsp;&nbsp;
        <el-input v-model="position" placeholder="请输入内容" type="text" style="width:200px;"></el-input>
        <el-button type="success" @click="passvalue">搜索</el-button>
      </div>
  </div>
</template>

<script>
export default {
    name:'positioning',
    data () {
        return {
            position:'天津',
            positiona:[],
            positionc:[],
            positioncc:[],
            positionb:1,
            positiond:[],
            weathera:['qing','yin','yun','yu'],
            positiondd:[],
            positioncccc:[],
            rainfall:[]
            }},
    methods:{
        passvalue:function(){
            this.$axios.get("https://tianqiapi.com/api?version=v6&appid=92838853&appsecret=Caj48NyM&city="+this.position).then(
            res=>{
                console.log(res.data)
                this.positiona=res.data;
                
            }
        )   
            

            this.$axios.get("https://tianqiapi.com/api?version=v1&appid=92838853&appsecret=Caj48NyM&city="+this.position).then(
            res=>{
                console.log(res.data.data)
                this.positionc=res.data.data;
                this.positioncc=res.data.data[0].wea_img;
                this.positionccc=res.data.data[0].hours;
                this.positionab=res.data.data[0].index;
                for (let index = 0; index < res.data.data.length; index++) {
                    this.positioncccc[index]=res.data.data[index].wea_img;
                    
                }
            }
            )

            this.hour=new Date().getHours();
            if (6<this.hour<19) {
                this.positionb=1;
            }else{
                this.positionb=2;
            }
            


            for ( let index=0; index<this.weathera.length; index++ ) {
                if (this.positioncc==this.weathera[index]) {
                    this.positiond[index]=1;
                }
            }

            for (let indexl = 0; indexl < this.positioncccc.length; indexl++) {
                for ( let index=0; index<this.weathera.length; index++ ) {
                    if (this.positioncccc[indexl]==this.weathera[index]) {
                        this.positiondd[indexl]=index;
                }}}


  


            bus.$emit('passvaluea',this.positiona)
            bus.$emit('passvalueb',this.positionb)
            bus.$emit('passvaluec',this.positionc)
            bus.$emit('passvalueccc',this.positionccc)
            bus.$emit('passvalued',this.positiond)
            bus.$emit('passvaluedd',this.positiondd)
            bus.$emit('passvalueab',this.positionab)
        }
    }
};
</script>
<style scoped>
h2{
    float: left;
}
.el-icon-location-outline{
    float: left;
    font-size:30px;
    margin:5px; 
}
.input{
    float:right;
    margin-top: 10px;
}
</style>