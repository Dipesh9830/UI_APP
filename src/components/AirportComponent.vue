<template>
  <div class="wrapper">
    <div v-for="airport in airports" :key="airport.abbreviation" class="airport">  
        <p>{{ airport.abbreviation }}</p>
        <p>{{ airport.name }}</p>
        <p>{{ airport.city }}</p>
    </div>
  </div>
</template>


<script>
import devairports from '@/../public/airports.development.mock'
import stageairports  from '@/../public/airports.staging.mock'

export default {
  
  computed: {
    airports() {
      // Check the environment variable and select the appropriate data
      console.log("Current enviornment" , process.env.VUE_APP_ENV);
      if (process.env.VUE_APP_ENV === 'development') {
        return devairports;
      } else if (process.env.VUE_APP_ENV === 'staging')
        return stageairports;
       else {
      return null
    
    }
    }
  }
}

</script>

<style>



#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 1rem;
  max-width: 960px;
  margin: 0 auto;
}

.airport {
  border: 3px solid;
  border-radius: .5rem;
  padding: 1rem;
}

.airport p:first-child {
  font-weight: bold;
  font-size: 2.5rem;
  margin: 1rem 0;
}

.airport p:last-child {
  font-style: italic;
  font-size: .8rem;
}
</style>