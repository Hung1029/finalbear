<template>

  <div class="ticket">
      <div class="home" @click="home">Back</div>
      <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
      <b-container class="bv-example-row">
          <p class="topic1">選擇場次</p>

    <form id="ticketform">
<p class="topic2">選擇票價和張數</p>

<img @click="chose" id="aa" src="../img/s1.png" >  
<img @click="oaooo" id="bb" src="../img/s2.png" >

<p class="text1">購買張數</p>
<img class="img3" src="../img/t1.png" alt="">

<div class="btn1">
<input type="radio"  value="0" name="ta" id="ro" checked><label @click="ft(0,0)" for="ro"><div class="num">0</div></label>
<input type="radio"  value="1" name="ta" id="r1" checked><label  @click="ft(0,1)" for="r1"><div class="num">1</div></label>
<input type="radio" value="2" name="ta" id="r2" checked><label  @click="ft(0,2)" for="r2"><div class="num">2</div></label>
<input type="radio"  value="3" name="ta" id="r3" checked><label  @click="ft(0,3)" for="r3"><div class="num">3</div></label>
</div>
<img class="img4" src="../img/t2.png" alt="">

<div class="btn2">
<input type="radio" name="tb" id="r00" checked><label v-on:click="ft(1,0)" for="r00"><div class="num">0</div></label>
<input type="radio"  name="tb" id="r01" checked><label  v-on:click="ft(1,1)" for="r01"><div class="num">1</div></label>
<input type="radio"  name="tb" id="r02" checked><label v-on:click="ft(1,2)" for="r02"><div class="num">2</div></label>
<input type="radio" name="tb" id="r03" checked><label v-on:click="ft(1,3)" for="r03"><div class="num">3</div></label>
</div>
<!-- <input class="submit" @click="submit" type="submit" value="確定購買"> -->
<button class="submit" v-on:click="submit"  >確定購買</button>
    </form>
    <p class="text2">購買張數</p>
    <p class="number1">目前剩下張數 : {{ count1 }}</p>
    <p class="number2">目前剩下張數 : {{ count2 }}</p>
    <!-- <p class="number" v-for="(item,index) in items" :key="item">目前剩下張數 : {{ item.count }}</p> -->
    </b-container>
   
  </div>
</template>
<script>
var i =0,j=0; var txt;
  export default {
    data () {
        return{
        c:[0,0],
        count1:2000,
        count2:3000,
        }
    },
    methods: {
        ft:function(index,val){
            if(index==0){
                this.count1+=this.c[index];
                this.c[index]=val;
                this.count1-=this.c[index];
            }
            else {
                this.count2+=this.c[index];
                this.c[index]=val;
                this.count2-=this.c[index];
            }
            // this.count[index]+=this.c[index];
            // this.c[index]=val;
            // this.count[index]-=val;
            // console.log(this.c);
            // console.log(this.count);
        },
        submit:function(){
            if(confirm("確定要訂購嗎?")){
                alert("訂購成功!");
            this.$router.replace('/')
            }
            else{
                count2=-this.c[index];
            this.$router.replace('/ticket')
            alert("訂購失敗!")
            }
        },
     home:function(){
            this.$router.replace('/')
          },
    chose:function(){
       
        if(i==0 && j==0){
        document.getElementById('aa').style.borderColor='rgb(181, 9, 67)';
        i=1;
        }
        else if(i==1 && j==0){
            document.getElementById('aa').style.borderColor='white';
            i=0;
        }
        else if(i==1 && j==1){
            document.getElementById('aa').sytle.borderColor='white';
            document.getElementById('bb').style.borderColor='rgb(181, 9, 67)';
            j=1;i=0;
        }
        else if(i==0 && j==1){
            document.getElementById('aa').style.borderColor='rgb(181, 9, 67)';
            document.getElementById('bb').style.borderColor='white';
            j=0;i=1;
        }
    },
    oaooo:function(){
        
        if(j==0 && i==0){
        document.getElementById('bb').style.borderColor='rgb(181, 9, 67)';
        j=1;
        }
        else if(j==1 && i==0){
            document.getElementById('bb').style.borderColor='white';
            j=0;
        }
        else if(i==1 && j==0){
            document.getElementById('bb').style.borderColor='rgb(181, 9, 67)';
            document.getElementById('aa').style.borderColor='white';
            j=1;i=0;
        }
        else if(j==0 && i==1){
            document.getElementById('bb').style.borderColor='rgb(181, 9, 67)';
            document.getElementById('aa').style.borderColor='white';
            j=1;i=0;
        }
    },
    

    } 
  }

</script>

<style scoped>
#alert{
    color:#fff;
    position: absolute;
    z-index: 3;
    font-family:'微軟正黑體';
    font-size:30px;
    padding-left:10px;
    background-color:rgb(181, 9, 67);
}
.number1{
     color:#fff;
    position: absolute;
    z-index: 3;
    font-family:'微軟正黑體';
    font-size:28px;
    left:1300px;
    top:1200px;
}
.number2{
     color:#fff;
    position: absolute;
    z-index: 3;
    font-family:'微軟正黑體';
    font-size:28px;
    left:1300px;
    top:1600px;
}

input[type="radio"] {
    margin-left:100px;
    width: 20px; height: 20px; opacity: 0; }
label {
    background-color:rgb(255, 255, 255);
    position: absolute;
    width: 80px; 
    height: 50px;
    border-radius: 10px;
    border: 1px solid rgb(255, 255, 255);
    
     } /*設置選中的input的樣式*/ /* + 是兄弟選擇器,獲取選中後的label元素*/ 


input:checked+label{
    background-color: rgb(181, 9, 67);
    border: 1px solid rgb(181, 9, 67); } 
input:checked+.num{
    color:cornsilk;

}


.num{
    position: relative;
    top:10px;
    left:33px;
    font-size:20px;
    font-family:Arial, Helvetica, sans-serif;
}


.btn1{
    position: relative;
    top:1200px;
    left:200px;
    z-index: 6;
}
.btn2{
    position: relative;
    top:1600px;
    left:200px;
    z-index: 6;
}
.submit{
    padding:15px;
    top:1850px;
    font-family:'微軟正黑體';
    color:#fff;
    position: absolute;
    font-size:20px;
    left:800px;
    width:120px;
    height:60px;
    background-color:rgb(181, 9, 67);
    z-index: 6;
    border-radius: 10px 10px 10px 10px;
}
.topic1{
    color:#fff;
    position: absolute;
    z-index: 3;
    font-family:'微軟正黑體';
    font-size:30px;
    left:250px;
    top:140px;
    padding-left:10px;
    border-left:rgb(181, 9, 67) 4px solid;
}
.topic2{
    color:#fff;
    position: absolute;
    z-index: 3;
    font-family:'微軟正黑體';
    font-size:30px;
    top:800px;
    left:250px;
    padding-left:10px;
    border-left:rgb(181, 9, 67) 4px solid;
}
.text1{
    color:#fff;
    position: absolute;
    z-index: 3;
    font-family:'微軟正黑體';
    font-size:28px;
    left:400px;
    top:1180px;
}
.text2{
    color:#fff;
    position: absolute;
    z-index: 3;
    font-family:'微軟正黑體';
    font-size:28px;
    left:400px;
    top:1600px;
   
}
#aa{
    border:4px rgb(255, 255, 255) solid;
    width:50%;
    position: absolute;
    top:50px;
    margin-top:10vw;
    border-radius: 22px;
}
#bb{
    border:4px rgb(255, 255, 255) solid;
    width:50%;
    top:10px;
    position: absolute;
    margin-top:25vw;
    border-radius: 22px;
}
.ticket{
    background-color:#000;
    height:2000px;
    background-image:url(../img/dark.jpg);
    background-repeat: no-repeat;
    background-attachment: fixed;
    background-position: center;
    background-size: cover;
}
.home{
    position: absolute;
    font-size:20px;
    width:120px;
    height:60px;
    background-color:rgb(181, 9, 67);
    z-index: 6;
    border-radius: 10px 10px 10px 10px;
}

.img3{
    width:50%;
    top:440px;
    position: absolute;
    margin-top:25vw;
}
.img4{
    width:50%;
    top:850px;
    position: absolute;
    margin-top:25vw;
}
</style>
