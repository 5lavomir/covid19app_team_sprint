<template>
    <div id="stats">
      <h1 class="mt-3 mb-5">&#8981; Select a Country</h1>
      <!-- Eventually the countries form the COVID19API should appear in the select dropdown -Lewis -->
      <select class="select mb-3" name="stats" @change="onSelectChange($event)" v-model="selectedCountry">
        <option v-for="listValue in valuesList" :value="listValue.country" :key="listValue.country">
            {{listValue.text}}
        </option>
      </select>
    </div>

  <!--Setting up a table for the information to be displayed -Andrew -->
    <table class="table table-striped table-bordered">
        <thead class="thead-dark">
            <tr>
                <th>Total Cases <br> {{ casesOnCountry.country }}</th>
                <th>Total Deaths <br> {{ casesOnCountry.country }}</th>
                <th>Total Recovered <br> {{ casesOnCountry.country }}</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>{{ casesOnCountry.confirmed }}</td>
                <td>{{ casesOnCountry.deaths }}</td>
                <td>{{ casesOnCountry.recovered }}</td>
            </tr>
        </tbody>
    </table>
</template>

<script>
// Import axios to get JSON information for the API -Lewis
import axios from 'axios'
// Sort the downdown from A -> Z -Lewis
import { sortBy } from 'lodash'

export default {
  name: 'Stats',
  data: function () {
    return {
      casesOnCountry: {
        country: '',
        confirmed: '0',
        deaths: '0',
        recovered: '0',
        active: 'Active'
      },
      valuesList: [{ country: 'Country', text: 'Country' }],
      selectedCountry: 'Country',
      hisoricalData: {
        data: {},
        options: {}
      }
    }
  },
  // No idea what async does, bring this up in the meeting, same for await -Lewis
  async created () {
  // Grabs the Json data for the Countries -Lewis
    const { data } = await axios.get('https://api.covid19api.com/countries')
    const allCountries = data.map(c => {
      return {
        country: c.Slug,
        text: c.Country
      }
    })
    // Will sort the countries from A -> Z
    this.valuesList = [{ country: 'Country', text: 'Choose a country' }, ...sortBy(allCountries, ['text'])]
  },
  methods: {
    async onSelectChange (event) {
      try {
        const country = event.target.value
        if (!country) return
        // We fetch the country's particular data
        // https://scotch.io/tutorials/asynchronous-javascript-using-async-await
        const { data } = await axios.get(` https://api.covid19api.com/total/country/${event.target.value} `)
        // Totals for the country selected
        this.showTotals(data)
      } catch (err) {
        console.log(err)
      }
    },
    showTotals (data) {
      // Grabs the last element of the data for the current date
      const totals = data[data.length - [1]]
      // Stores the selected country's first letter capitalized
      const countryFL = this.selectedCountry.charAt(0).toUpperCase()
      // Stores the selected country's full name, minus the first character
      const country = this.selectedCountry.slice(1)

      this.casesOnCountry = {
        country: countryFL + country,
        confirmed: totals.Confirmed,
        deaths: totals.Deaths,
        recovered: totals.Recovered,
        active: totals.Active
      }
    }
  }
}
</script>

<style>
.table{
  table-layout: fixed;
  background-color: rgb(114, 141, 150);
  width: 70%;
  margin-left: 15%;
  margin-top: 15px;
}

tbody{
  color: white;
}

th, td {
  text-align: center;
  font-size: 25px;
}

select{
  font-size: 15px;
  color: black;
  padding: 3px;
  cursor: pointer;
  border: solid 2px gray;
}

select:hover{
  background-color: rgb(151, 151, 151);
  color: white;
  border: solid 2px rgb(0, 255, 179);
}

option{
  background-color: white;
  color: black;
}
</style>
