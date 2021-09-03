<template>
<div>
  <div class="main">
 <v-container>
    <v-row class="text-center">
      <v-col cols="12" >
       <div class="launch px-16 ">WE'RE LAUNCHING SOON 2030</div>
      </v-col>
    </v-row>
     <v-container class="">
      <v-layout row wrap >
          <v-flex xs3><div class="box mx-2"><v-card color="hsl(236, 21%, 26%)" class="  py-1 font-weight-bold  round " width="120px" ><v-container class=""><div class="down text-center">{{day}}</div><v-row><v-col><div class="count text-center"> DAYS </div></v-col></v-row> </v-container></v-card></div></v-flex>
          <v-flex xs3><div class="box mx-2"><v-card color="hsl(236, 21%, 26%)" class="  py-1 font-weight-bold  round " width="120px" ><v-container class=""><div class="down text-center">{{hours}}</div><v-row><v-col><div class="count text-center"> HOURS </div></v-col></v-row> </v-container></v-card></div></v-flex>
          <v-flex xs3><div class="box mx-2"><v-card color="hsl(236, 21%, 26%)" class="  py-1 font-weight-bold  round " width="120px" ><v-container class=""><div class="down text-center">{{min}}</div><v-row><v-col><div class="count text-center"> MINUTES </div></v-col></v-row> </v-container></v-card></div></v-flex>
          <v-flex xs3><div class="box mx-2"><v-card color="hsl(236, 21%, 26%)" class="  py-1 font-weight-bold  round " width="120px" ><v-container class=""><div class="down text-center ">{{sec}}</div> <v-row><v-col><div class="count text-center"> SECONDS</div></v-col></v-row> </v-container></v-card></div></v-flex>
      </v-layout>
      </v-container>

  </v-container>
  <div class="ico">
    <span>
      <v-btn class="b" text  elevation="" color="hsl(345, 95%, 68%)"> 
        <v-icon color="grey">
          fa-facebook
        </v-icon>
      </v-btn>
    </span>
    <span>
      <v-btn  class="b" text  elevation="" color="hsl(345, 95%, 68%)"> 
        <v-icon color="grey">
          fa-instagram
        </v-icon>
      </v-btn>
    </span>
    <span>
      <v-btn class="b" text  elevation="" color="hsl(345, 95%, 68%)"> 
        <v-icon color="grey">
          fa-pinterest
        </v-icon>
      </v-btn>
    </span>
    </div>
  </div>
</div>
</template>

<script>
  export default {
    name: 'HelloWorld',

    data: () => ({
      day:0,
      hours:0,
      min:0,
      sec:0

    }),
    created(){
      setInterval(()=>{
        let destination = new Date(2030, 0 , 1)
        let recent = new Date()

        let destime = destination.getTime() - recent.getTime()
        let s = Math.floor(destime/1000)
        let m = Math.floor(s/60)
        let h = Math.floor(m/60)
        let d = Math.floor(h/24)
        h %= 24
        m %= 60
        s %= 60
        h = (h  < 10) ? '0' + h: h
        m = (m  < 10) ? '0' + m: m
        s = (s  < 10) ? '0' + s: s
        this.day = d
        this.hours = h
        this.min = m
        this.sec = s
       
      },1000)
    }
  }
</script>
<style scoped>
.main{
  width: 100%;
  height: 100vh;
  background-image: url('../assets/bg-stars.svg');
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  background-color: hsl(235, 16%, 14%) ;
  overflow: hidden;
  position: relative;
}
.main::after{
  display: block;
  position: absolute;
  bottom: 0%;
  width: 100%;
  content: url('../assets/pattern-hills.svg');
}
.launch{
  font-family: manrope;
  font-weight: lighter;
  text-shadow: -2px -2px 3px rgba(214, 207, 207, 0.5);
  color: hsl(0, 0%, 100%);
  font-size: 1.5em;
  padding: 4em 0;
  
}
.down{
  /* border: solid 1px red; */
  /* padding: 20px; */
  /* font-weight: bold; */
  font-size: 2em;
  font-family: montserrat;
  color: hsl(345, 95%, 68%);

  /* border-radius: 15px; */
}
.count{
  font-family: roboto;
  color: hsl(0, 0%, 100%);
   font-weight: lighter;
   font-size: 0.8em;
}
.round.v-card{
  border-radius: 20px;
} 
.box{
  box-shadow: 0px 4px 5px black;
  width: 120px;
  border-radius: 20px;

}
.ico{
  padding: 0 40%;
  width: 100%;
  position: absolute;
  top: 85%;
  z-index: 100;
}
@media screen and (max-width: 600px) {
 .down{
  color: hsl(345, 95%, 68%);

  /* border: solid 1px red; */
  /* font-weight: bold; */
  font-size: 0.6em;
  font-family: montserrat;
  /* border-radius: 5px; */
}
.count{
  font-size: 0.4em;

  font-family: roboto;
  color: hsl(0, 0%, 100%);
   font-weight: lighter;
}
  .ico{
  padding: 0 20%;
  width: 100%;
  position: absolute;
  top: 85%;
  z-index: 100;
} 
.box{
  box-shadow: 0px 4px 5px black;
  width: 65px;
  border-radius: 20px;

}
  
}
@media screen and (min-width: 600px) {

    .ico{
  padding: 0 35%;
  width: 100%;
  position: absolute;
  top: 85%;
  z-index: 100;
} 
}

</style>