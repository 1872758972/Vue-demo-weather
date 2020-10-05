<template>
    <div>
        <p style="font-size:20px;">&nbsp;&nbsp;&nbsp;全国降雨量预报图</p><br><br>
        <div class="scrp"><p>24小时</p><br><br><el-image class="scro" src="https://pi.weather.com.cn/i/product/pic/l/sevp_nmc_stfc_sfer_er24_achn_l88_p9_20200929060002400.jpg" ></el-image></div>
        <div class="scrp"><p>48小时</p><br><br><el-image class="scro" src="https://pi.weather.com.cn/i/product/pic/l/sevp_nmc_stfc_sfer_er24_achn_l88_p9_20200929000004800.jpg" ></el-image></div>
        <div class="scrp"><p>72小时</p><br><br><el-image class="scro" src="https://pi.weather.com.cn/i/product/pic/l/sevp_nmc_stfc_sfer_er24_achn_l88_p9_20200929000007200.jpg" ></el-image></div>
    </div>
</template>

<script>
export default {
    name:'rainfall',
    data () {
        return {
        }
    }
}
</script>

<style>
.scrp p{
    font-size: 17px;
    margin-left: 140px;
}
.scro{
    width: 380px;
    height: 380px;
}
.scrp{
    float: left;
    margin-left: 40px;
}
</style>