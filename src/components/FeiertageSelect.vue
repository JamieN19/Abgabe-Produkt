<template>
  <h1>Monat</h1>
  <input v-model="monat">
  <p>{{ monat }}</p>
  <tr v-for="feiertag in feiertage" :key="feiertag.countries">
    <td>{{feiertag.countries}}</td>
  </tr>
  
</template>

<script>

export default {
  name: "MonatSelect",
  data() {
    return{
      feiertage: [],
      monat: ''
      
    }

  },
  created() {
    this.getHolidays()
  },
  methods: {
    async getHolidays(){
      const response = await fetch('https://holidayapi.com/v1/holidays?pretty&key=dcaea857-cdbe-46cb-83af-da80d77c5d78&country=CH&year=2021');
      this.feiertage = await response.json();    
      console.log(JSON.stringify(this.feiertage)); 
    }
  }
};
</script>

<style>
</style>