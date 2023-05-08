<template>
  <div class="content">
    <div class="main d-flex">  <div class="left">
      <p>Bill</p>
      <input type="number"  placeholder="0" v-model="bill" />
      <p>Select Tip %</p>
      <button class="btn" @click="handleButtonClick('5')" >5%</button>
      <button class="btn" @click="handleButtonClick('10')">10%</button>
      <button class="btn" @click="handleButtonClick('15')">15%</button>
      <br />
      <button class="btn"  @click="handleButtonClick('15')" >25%</button>
      <button class="btn" @click="handleButtonClick('50')">50%</button>
      <input
      v-model="percent"
        class="custom"
        type="text"
        placeholder="  Custom
"
      />
      <p>Number of People</p>
      <input type="number" v-model="people" placeholder="0"/>
    </div>

    <div class="right">
      <div class="d-flex justify-content-between">
        <div>
          <h6>Tip Amount</h6>
          <p class="same">/ person</p>
        </div>
        <div>
          <h5 >           {{ tip }}
          </h5>
        </div>
      </div>

      <div class="d-flex justify-content-between">
        <div>
          <h6>Total</h6>
          <p>/ person</p>
        </div>
        <div>
          <h5 class="same">{{total}}</h5>
          </div>
      </div>

      <button @click="resetFields" class="btn-block btn reset" >Reset</button>
    </div></div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      bill: '',
      percent:'',
      people:1
    };
  },
  methods: {
    handleButtonClick(value) {
  this.percent = parseInt(value)
  return console.log(this.percent)
  
    },
    resetFields(){
      this.bill='',
      this.percent=''
    }
  },
  computed:{
    tip(){
      return parseInt(this.percent /100*this.bill)
    }, 
    total(){
      return this.tip += this.bill / this.people
    }
  }
};
</script>


<style>

body{
  background-color: hsl(185, 41%, 84%);
}
.main{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: white;
  border-radius: 10px;

}

.left{
color: hsl(186, 14%, 43%); 
padding: 10px;
width: 400px;

}
input{
border-width: 0;
background-color: hsl(189, 41%, 97%);
}
button{
  background-color: hsl(183, 100%, 15%) ;
  color: white;
  width: 50px;
  border: 0;
  border-radius: 2px;
  padding: 10px;
  margin: 2px;
}
.custom{
  width: 50px;
  border: 0;
  border-radius: 2px;
  padding: 10px;
  margin: 2px;

}
.right{
  background-color:  hsl(183, 100%, 15%);
  padding: 10px;
  border-radius: 10px;
  width: 300px;
}
h5 {
  color: hsl(172, 67%, 45%);
}
h6{
  color: white;
}

.reset{
  background-color: hsl(172, 67%, 45%);
  color: hsl(183, 100%, 15%);
}
</style>