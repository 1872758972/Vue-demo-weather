<template>
    <div class="hourweather">
        <div class="hourp"><br>&nbsp;&nbsp;&nbsp;<p>逐小时预报</p></div>
        <div class="hourl">
            <li v-for="user in positionp">
                <p class="txttime">{{ user.day}}</p><br>&nbsp;
                <i class=" iconfont " :class="[positiono[0]==1? 'icon-qing' : '']"></i>
                <i class=" iconfont " :class="[positiono[1]==1? 'icon-duoyun' : '']"></i>
                <i class=" iconfont " :class="[positiono[2]==1? 'icon-yintian' : '']"></i>
                <i class=" iconfont " :class="[positiono[3]==1? 'icon-yuyutianxiayuxianxing' : '']"></i><br>
                &nbsp;&nbsp;&nbsp;<p class="txtdegree">{{ user.tem}}</p>
            </li>
        </div>
    </div>
</template>

<script>
export default {
    name:'hourweather',
    data () {
        return {
            positionp:[],
            positiono:[]
        }
    },
    mounted(){
        bus.$on('passvalueccc',(value)=>{
            this.positionp=value;
        })
        bus.$on('passvalued',(value)=>{
            this.positiono=value;
        })
    }
}
</script>

<style>
li{
    list-style-type:none;
    float: left;
    margin-right: 30px;
    margin-left: 50px;
    margin-top: 20px;
}
.hourl{
    margin-left: 40px;
}
.hourl i{
    font-size: 50px;
    color: cornflowerblue;
}
.hourp{
    margin-top:10px;
}
.hourp p{
    font-size: 20px;
}
</style>