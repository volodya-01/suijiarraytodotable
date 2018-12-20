<template>
   <div>
     <div class="outbox">
      <div class="inbox">
        <div class="contentrbox" v-for="(itemtr,indextr) in stu" :key="indextr.id" :class="indextr==bgcolor?'zero':''">
          <div class="con1 con">{{itemtr.MeterName}} </div>
          <div class="con2 con">{{itemtr.MeterNum}}</div>
          <div class="con3 con">{{itemtr.X}}</div>
           <div class="con4 con">{{itemtr.Y}}<img :src="stu[indextr].img1" alt=""></div>
       
        </div>
      </div>
   </div>
 
   <div class="demobox">
     <demo1/>
     <picdata/>
   </div>
   </div>
</template>

<script>
import demo1 from '@/components/demo1'
import picdata from '@/components/picdata'
import img1 from "../assets/on.png";
import img2 from "../assets/深水_日常调度_切图01_24-1.png";
export default {
  name: "HelloWorld",
  data() {
    return {
      stu:[],
      bgcolor:'',
       photoData: [img1,img2]
    };
  },
 components:{
   demo1,
   picdata
 },
 mounted(){
   var that=this;
   that.sortdata();
   setInterval (function(){
     that.sortdata();
   },1000)
  },
 methods:{
   sortdata() {
      var that=this;
      var a = [
        {
          MeterName: "国际财富中心",
          MeterNum: "HD72_2069_A13|",
          X: 501755.29101,
          Y: 329760.99732,
          img1,img2
        },
        {
          MeterName: "群贤路解放路口",
          MeterNum: "HD72_182_A13|",
          X: 499574.64266,
          Y: 327542.05546,
          img1,img2
        },
        {
          MeterName: "赵墅桥",
          MeterNum: "HD72_2067_A13|",
          X: 500974.3172,
          Y: 324923.65399,
          img1,img2
        },
        {
          MeterName: "马山流量2",
          MeterNum: "HD72_195_A2|",
          X: 506234.86543,
          Y: 328704.91301,
          img1,img2
        },
        {
          MeterName: "鸿通金都",
          MeterNum: "HD72_2017_A2|",
          X: 503489.03919,
          Y: 329400.14815,
          img1,img2
        },
        {
          MeterName: "汤公路群贤路口",
          MeterNum: "HD72_184_A2|",
          X: 500904.77677,
          Y: 327680.95673,
          img1,img2
        },
        {
          MeterName: "洋江东路",
          MeterNum: "HD72_2068_A13|",
          X: 501056.27212,
          Y: 325865.79768,
          img1,img2
        },
        {
          MeterName: "洋江路绍三线口",
          MeterNum: "HD72_121_A13|",
          X: 500924.77576,
          Y: 325856.26992,
          img1,img2
        },
        {
          MeterName: "育贤路南",
          MeterNum: "HD72_197_A1|",
          X: 505928.55945,
          Y: 327281.35661,
          img1,img2
        },
        {
          MeterName: "329调流阀前",
          MeterNum: "HD72_139_A3",
          X: 501836.79373,
          Y: 329975.85048,
          img1,img2
        },
        {
          MeterName: "世纪街东安村(2H)",
          MeterNum: "R_PTA_40148_A5",
          X: 504922.47284,
          Y: 328642.01485,
          img1,img2
        },
        {
          MeterName: "世纪街美安居(2H)",
          MeterNum: "R_PTA_40200_A5",
          X: 505208.63626,
          Y: 328829.36433,
          img1,img2
        },
        {
          MeterName: "咸亨水质",
          MeterNum: "RPS600_69_A1",
          X: 501183.32154,
          Y: 326657.30041,
          img1,img2
        },
        {
          MeterName: "群贤路汤公路口",
          MeterNum: "HD72_2008_A4",
          X: 500905.00419,
          Y: 327681.8421,
          img1,img2
        },
        {
          MeterName: "育贤路九城公园北(2H)",
          MeterNum: "R_PTA_40149_A5",
          X: 504929.16833,
          Y: 327883.07937,
          img1,img2
        },
        {
          MeterName: "赵墅桥压力",
          MeterNum: "HD72_2107_A1",
          X: 500969.85732,
          Y: 324973.51612,
          img1,img2
        },
        {
          MeterName: "越东小区",
          MeterNum: "RPS600_70_A1",
          X: 503195.17079,
          Y: 327978.89929,
          img1,img2
        },
        {
          MeterName: "马山调流阀前",
          MeterNum: "HD72_138_A3",
          X: 506241.96046,
          Y: 328696.9803,
          img1,img2
        },
        {
          MeterName: "马山调流阀后",
          MeterNum: "HD72_138_A1",
          X: 506242.21922,
          Y: 328698.31206,
          img1,img2
        },
        {
          MeterName: "329调流阀后",
          MeterNum: "HD72_139_A1",
          X: 501831.92442,
          Y: 329976.54134,
          img1,img2
        }
      ];
      var arr = a;
      var random = [];
      var len = a.length;
      for (var i = 0; i < len; i++) {
        var index = Math.floor(Math.random() * (len - i));
        random.push(a[index]);
        arr.splice(index, 1);
      }
      that.bgcolor=Math.floor(Math.random()*10)
      that.stu=random;
      console.log(that.bgcolor);
      return random;
    }
 }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.outbox {
  height: 500px;
  width: 900px;
  /* background-color: aqua; */
  margin: 0 500px;
  background-color: rgb(50, 51, 51, 0.8);
  overflow: auto;
}
.inbox {
  height: 100%;
  width: 100%;
}
.contentrbox {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: row;
  flex-direction: row;
  -ms-flex-wrap: nowrap;
  flex-wrap: nowrap;
  -webkit-box-pack: space-around;
  -ms-flex-pack: space-around;
  justify-content: space-around;
  -webkit-box-align: start;
  -ms-flex-align: start;
  align-items: flex-start;
  height: 40px;
  width: 100%;
  margin-bottom: 5px;
  background-color: rgb(186, 186, 197, 0.8);
}
.con {
  height: 40px;
  width: 25%;
  text-align: start;
  line-height: 40px;
}
.con1 {
  margin-left: 20px;
}
.zero{background: red}
.demobox{
  margin-top: 40px;
}
</style>
