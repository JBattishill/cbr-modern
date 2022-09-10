<!-- this component can hold site navigation -->
<!-- if we put it here we can avoid having to repeat the code -->
  <template>
  <div class="container-fluid">
    <ul class="nav nav-tabs justify-content-end">
      <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/events">
          2022
        </NuxtLink>
      </li>
      <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/events/2021">
          2021
        </NuxtLink>
      </li>
      <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/events/2020">
          2020
        </NuxtLink>
      </li>
      <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/events/2019">
          2019
        </NuxtLink>
      </li>
      <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/events/2018">
          2018
        </NuxtLink>
      </li>
      <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/events/2017">
          2017
        </NuxtLink>
      </li>
  </ul>
  </div>  
</template>

<style scoped>
 @import url('~assets/css/style.css');
</style>

<!-- this component can hold site navigation -->
<!-- if we put it here we can avoid having to repeat the code 
<template>
    <div class="container-fluid">
      <ul class="nav nav-tabs justify-content-end">
        <li class="nav-item">
          <button class="2022 btn btn-outline-dark m-2" @click="event2021">2022</button>
        </li>
        <li class="nav-item">
          <button class="2021 btn btn-outline-dark m-2" @click="event2021">2021</button>
        </li>
        <li class="nav-item">
          <button class="2020 btn btn-outline-dark m-2" @click="event2020">2020</button>
        </li>
        <li class="nav-item">
          <button class="2019 btn btn-outline-dark m-2" @click="event2019">2019</button>
        </li>
        <li class="nav-item">
          <button class="2018 btn btn-outline-dark m-2" @click="event2018">2018</button>
        </li>
        <li class="nav-item">
         <button class="2017 btn btn-outline-dark m-2" @click="event2017">2017</button>
        </li>
    </ul>
    <h2>Attempting to fetch data from {{ year }} </h2>
    <p> The year is currently {{currentYear}}</p> -->