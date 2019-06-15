<template>
    <div class="home">
      <div class="logout" @click="logout">Logout</div>
        <div class="logo">
            <img src="../img/LOGO.png" alt="">
        </div>
          <!-- <div id="oao">
          <input type="button" style="width:50px height:50px border:1px #fff none;background-color:rgba(58, 57, 57, 0.63)" id="bye" name="bye" value="Ⅹ" @click="bye()">
        </div> -->
        <div class="butten" id="butten">
             <a href="javascript:void(0)" @click="change()"> <p>我要訂票</p></a>
        </div>
        
        <div class="home_img">
            <img src="../img/IMG1.jpg" alt="">
        </div>

        <div class="tp">
            <p>樂團簡介 ‧ Band Introduction</p>
        </div>
        
        <div class="text1">
            <p>老熊與我<br><br>成立於2018/10 國立台北教育大學<br>希望透過音樂喚醒現代文明人的野性與熱情<br>由四名學生組成，卻演奏出無與倫比的樂曲<br>駕馭許多不同風格的音樂<br>在創作及比賽中屢勝佳績<br>單曲《野性呼喚》、《阿偉你的狗在叫你》廣受好評!</p>
        </div>
        <div class="span1"></div>
        <div class="span2"></div>
        <div class="circle1" id="circle1">
            <div class="name1">蜂蜜熊熊</div>
            <img src="../img/bear.jpg.png" alt="">
        </div>
        
        <div class="circle2" id="circle2">
            <div class="name2">地瓜葉女神</div>
            <img src="../img/47c.jpg.png" alt="">
        </div>
        
        
        <div class="circle3" id="circle3">
            <div class="name3">漩渦碩人</div>
            <img src="../img/old.jpg.png" alt="">
        </div>
        <div class="circle4" id="circle4">
            <div class="name4">大馬來人</div>
            <img src="../img/m.jpg.png" alt="">
        </div>
        <div class="tp2">
            <p>演唱會資訊 ‧ Information</p>
        </div>
    </div>
</template>
<script>
export default {
  name:'home',
  methods: {
    change:function(){
      this.$router.push('ticket');
    },
    logout: function() {
      firebase.auth().signOut().then(() => {
        this.$router.replace('login')
      })
    }
    // ticket:function(){
    //   document.querySelector('#oao').style.display = "block";
    // },
    // bye:function(){
    //   document.querySelector('#oao').style.display = "none";
    // },
  }
}
</script>

<style scoped>

/* #oao{
top:50px;
right:400px;
left:400px;
display:none;
position: fixed;
z-index:5;
background-color:rgba(31, 22, 25, 0.651);
border:1px rgba(102, 99, 99, 0.425) solid;
width:600x;
height:600px;

} */
.logout{
  position: absolute;
    font-size:20px;
    width:120px;
    height:60px;
    background-color:#B50943;
    z-index: 6;
    border-radius: 10px 10px 10px 10px;
}
.name4{
    color:#fff;
    position: absolute;
    z-index: 3;
    font-family:'微軟正黑體';
    font-size:20px;
    top:90px;
    left:56px;
    display:none;
}
.name3{
    color:#fff;
    position: absolute;
    z-index: 3;
    font-family:'微軟正黑體';
    font-size:20px;
    top:90px;
    left:56px;
    display:none;
}
.name2{
    color:#fff;
    position: absolute;
    z-index: 3;
    font-family:'微軟正黑體';
    font-size:20px;
    top:90px;
    left:45px;
    display:none;
}
.name1{
    color:#fff;
    position: absolute;
    z-index: 3;
    font-family:'微軟正黑體';
    font-size:20px;
    top:90px;
    left:54px;
    display:none;
}
.home{
    margin:-8px;;
    height:4000px;
    background:#000;
    right:0;
    left:0;
}
.logo{
    right:0;
    position: absolute;
    z-index: 1;
}
.home_img {
    display:grid;
    grid-template-columns:100%;
    z-index: 0;
    max-width: 100%;
    top:-3vw;
    left:0;
    right:0;
    height: auto;
    position: absolute;
    overflow: hidden;
    }
.butten{
    position: absolute;
    font-size:20px;
    margin-top: 700px;
    margin-left:calc( (100vw - 200px) / 2 ); 
    width:180px;
    height:60px;
    background-color:#B50943;
    z-index: 1;
    border-radius: 10px 10px 10px 10px;
    }
    
.butten p{
    font-family:'微軟正黑體';
    font-size:27px;
    color:#fff;
    position: absolute;
    top:-17px;
    left:33px;
    }
#circle4:hover .name4{
        display:block;
}
#circle3:hover .name3{
        display:block;
}
#circle2:hover .name2{
        display:block;
    }
#circle1:hover .name1{
        display:block;
}
.butten:hover{
    opacity: 0.8;
}    
    
    
.tp{
    position: absolute;
    font-size:2vw;
    margin-top:900px;
    margin-left:50px;
    width:350px;
    z-index: 2;
    color:#fff;
  font-family:'微軟正黑體';
  border-left:8px #B50943 solid;
}
.text1{
    position: absolute;
    font-size:1.5vw;
    margin-top:1050px;
    margin-left:70px;
    width:450px;
    height:25vw;
    z-index: 2;
   
    color:rgb(207, 205, 205);
    font-family:'微軟正黑體';
}
.span1{
    position: absolute;
    z-index: 2;
    background-color:rgba(92, 90, 90, 0.89);
    width:100%;
    height:2px;
    top:850px;
}
.span2{
   position: absolute;
    z-index: 2;
    background-color:rgba(92, 90, 90, 0.89);
    width:100%;
    height:2px;
    top:1550px; 
}
.circle1{
    position: absolute;
    z-index: 2;
    background-color:#000;
    width:15vw;
    height:15vw;
    right:7vw;
    top:1000px;
    border-radius: 50%;
    overflow:hidden;
    border:3px rgba(92, 90, 90, 0.89) solid;
}
.circle1 img{
     position: absolute;
    right:-15px;
    top:-30px;
    opacity: 0.9;
    
}
.circle2 img{
    opacity: 0.9;
    position: absolute;
    right:-16px;
    top:-30px;
}
.circle2 img:hover{
opacity:0.7;
}
.circle1 img:hover{
opacity:0.7;
}
.circle3 img:hover{
opacity:0.7;
}
.circle4 img:hover{
opacity:0.7;
}
.circle2{
     position: absolute;
    z-index: 2;
    background-color:#000;
    width:15vw;
    height:15vw;
    right:28vw;
    top:1000px;
    border-radius: 50%;
    overflow:hidden;
    border:3px rgba(92, 90, 90, 0.89) solid;
}
.circle3{
    position: absolute;
    z-index: 2;
    background-color:#000;
    width:15vw;
    height:15vw;
    right:28vw;
    top:1250px;
    border-radius: 50%;
    overflow: hidden;
    border:3px rgba(92, 90, 90, 0.89) solid;
}
.circle3 img{
    position: absolute;
    right:-20px;
    top:-35px;
    opacity: 0.9;
}
.circle4{
   position: absolute;
    z-index: 2;
    background-color:#000;
    width:15vw;
    height:15vw;
    right:7vw;
    top:1250px;
    border-radius: 50%; 
    border:3px rgba(92, 90, 90, 0.89) solid;
    overflow: hidden;
}
.circle4 img{
    position: absolute;
    top:-10px;
    right:-60px;
    opacity: 0.9;
}
.tp2{
position: absolute;
    font-size:2vw;
    margin-top:1600px;
    margin-left:50px;
    width:300px;
    z-index: 2;
    color:#fff;
  font-family:'微軟正黑體';
   border-left:8px #B50943 solid;
}
</style>