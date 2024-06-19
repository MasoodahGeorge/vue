<template>
  <div class="about">
    <button @click="increment">Increment</button>
    <h1>
      counter-> <span>{{ counter }}</span>
    </h1>
    <button @click="decrement">Decrement</button>
  </div>
  <img :src="imgUrl" />
  <div>
    <!-- class styling binding -->
    <h4 :class="{ hello: check }">Conditional rendering</h4>

    <!-- conditional rendering -->
    <h1 v-if="check">The value is true</h1>
    <h1 v-else>The value is false</h1>
    <button @click="change()">Change state</button>

    <!-- conditional rendering -->
    <h1 v-show="check">This contains the v-show</h1>
    <ul>
      <!-- <li v-for="(sport,index) in sports" :key="index">{{sport}}</li> -->
      <li v-for="object in objects" :key="object.id">{{ object.message }}</li>
    </ul>

    <!-- oneWay data binding -->
    <h3>{{ oneWayText }}</h3>
    <!-- oneWay data binding -->
    <h3>{{ twoWayText }}</h3>
    <input type="text" v-model="twoWayText" />
  </div>

  <!-- <info-comp first-name="hehe" last-name="hehehehe"/>
  <info-comp first-name="hehe1"/>
  <info-comp :object-data="singleOject"/> -->
  <info-comp>
    Hehe I am using slots(sauur slay)
  </info-comp>

  <!-- <slot-comp> -->
  <slot-comp>
    <template #slotTitle>
      <!-- Card Slot -->
    </template>
    <template #default>
      <!-- <img :src="imgUrl"> -->
    </template>
  </slot-comp>
</template>
<script>
import InfoComp from '../components/infoComp.vue'
import SlotComp from '../components/slotComp.vue'
// import ProductView from './productView.vue';
export default {
  data() {
    return {
      counter: 0,
      imgUrl:"https://www.washingtonpost.com/wp-apps/imrs.php?src=https://arc-anglerfish-washpost-prod-washpost.s3.amazonaws.com/public/FPGDGYJXM56KI5CTHHDX3DN2WQ.jpg&w=1440",
      check: true,
      sports: ["soccer", "netball", "volleyball"],
      objects: [
        { message: "Hello there 1", id: 1 },
        { message: "Hello there 2", id: 2 },
        { message: "Hello there 3", id: 3 },
      ],
      singleOject:{
        name:'Masoodah',
        surname:'George'
      },
      oneWayText:'hehe',
      twoWayText:'hehe2.0'
    };
  },
  components:{
    InfoComp,
    SlotComp,
    // ProductView
  },
  methods: {
    increment() {
      this.counter++;
    },
    decrement() {
      this.counter--;
    },
    change() {
      this.check = !this.check;
    },
  },
};
</script>

<style scoped>
h1 {
  color: pink;
}
img {
  width: 300px;
  padding-top: 0.5%;
}
li {
  text-decoration: none;
}
</style>