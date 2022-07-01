<template>
  <img alt=" logo" src="../assets/logo.png">

  <div class="form">
    <feiertage-select></feiertage-select>
    <monat-select></monat-select>
    <label for="from">Von:</label>
    <input if="from" type="date" v-model="fromDate"/>
    <label fro="to">Bis:</label>
    <input it="to" type="date" v-model="toDate"/>
  </div>
  <div class="home-buttons">
    <button class="btn btn-primary" @click="doReserve">Reserve</button>
  </div>

</template>

<script>
// @ is an alias to /src
import FeiertageSelect from '@/components/FeiertageSelect.vue'
import MonatSelect from '@/components/MonatSelect.vue'
import { store } from '@/store'
export default {
  name: 'HomeView',
  data() {
    return {
      store,
      fromDate: null,
      toDate: null,
    };
  },
  components: {
    FeiertageSelect,
    MonatSelect,
  },
  methods: {
    async doReserve() {
      const payload = {
        StudentID: store.lernpartner_id,
        EquipmentID: store.equipment_id,
        Start: this.fromDate,
        End: this.toDate,
      };
      console.log(payload);
      const response = await fetch('https://holidayapi.com/v1/holidays?pretty&key=dcaea857-cdbe-46cb-83af-da80d77c5d78&country=CH&year=2021', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify(payload)
      });
      const result = await response.json();
      alert(result.result);
    }
  },
}
</script>

<style lang=sass scoped>
  .form
    width: 80%
    display: grid
    grid-template-columns: 0.4fr 0.5fr
    gap: 1em

</style>
