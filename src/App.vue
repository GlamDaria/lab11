<template>
  <div id="app">
    <div
      id="sensorWrap"
      v-for="sensor in myCollectionOfBeautifulSensors"
      :key="sensor.id"
    >
      <Sensor 
      :id="sensor.id" :title="sensor.title" 
      @removeSensor="remove"
      />
    </div>
    <div class="input-group mb-3">
      <h2>Add a New Sensor</h2>
      <input type="text" class="form-control mt-3" placeholder="Enter Title" aria-label="Title" aria-describedby="basic-addon1" v-model="newBeautifulSensor" required>
      <button type="button" class="btn btn-info mt-3" @click="addSensor">Add</button>
    </div>
  </div>
</template>

<script>
import Sensor from "./components/Sensor.vue";

export default {
  name: "app",
  data: () => ({
    myCollectionOfBeautifulSensors: [
      {
        id: 0,
        title: "First beautiful sensor"
      },
      {
        id: 1,
        title: "Second beautiful sensor"
      },
      {
        id: 2,
        title: "Third beautiful sensor"
      },
      {
        id: 3,
        title: "Forth beautiful sensor"
      },
      {
        id: 4,
        title: "Fifth beautiful sensor"
      },
      {
        id: 5,
        title: "Sixth beautiful sensor"
      },
      {
        id: 6,
        title: "Seventh beautiful sensor"
      },
      {
        id: 7,
        title: "Eighth beautiful sensor"
      },
      {
        id: 8,
        title: "Nineth beautiful sensor"
      },
      {
        id: 9,
        title: "Tenth beautiful (ugly) sensor"
      },
    ],
    newBeautifulSensor: null,
    counter: 9,
  }),
  components: {
    Sensor
  },
  methods: {
    remove(e) {
      this.myCollectionOfBeautifulSensors = this.myCollectionOfBeautifulSensors.filter((el) => {
        return el.id != e
      });
    },
    addSensor() {
      this.counter++;
      this.myCollectionOfBeautifulSensors.push({ id: this.counter, title: this.newBeautifulSensor })
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
  align-items: center;
}

.input-group {
  margin: 2rem;
  display: flex;
  flex-flow: column nowrap;
  justify-content: space-around;
}

.form-control {
  width: 100% !important;
}
</style>
