<!-- this component can hold site navigation -->
<!-- if we put it here we can avoid having to repeat the code -->
<template>
    <div class="container-fluid">
      <ul class="nav nav-tabs justify-content-end">
        <li class="nav-item">
          <NuxtLink class="btn btn-outline-dark m-2" to="/events">
              Events
            </NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink class="btn btn-outline-dark m-2" to="/events/2017" @click="toggle($event)">
            2017
          </NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink class="btn btn-outline-dark m-2" to="/events/2018" @click="toggle($event)">
            2018
          </NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink class="btn btn-outline-dark m-2" to="/events/2019" @click="toggle($event)">
            2019
          </NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink class="btn btn-outline-dark m-2" to="/events/2020" @click="toggle($event)">
            2020
          </NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink class="btn btn-outline-dark m-2" to="/events/2021" @click="toggle($event)">
            2021
          </NuxtLink>
        </li>
    </ul>
    </div>  
  </template>
  
  <script></script>