<!-- this component can hold site navigation -->
<!-- if we put it here we can avoid having to repeat the code -->
<template>
    <div class="container-fluid">
      <ul class="nav nav-tabs justify-content-end">
        <li class="nav-item">
          <NuxtLink class="btn btn-outline-dark m-2" to="/">
              Home
            </NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink class="btn btn-outline-dark m-2" to="/events/2016">
            2016
          </NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink class="btn btn-outline-dark m-2" to="/events/2017">
            2017
          </NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink class="btn btn-outline-dark m-2" to="/events/2018">
            2018
          </NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink class="btn btn-outline-dark m-2" to="/events/2019">
            2019
          </NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink class="btn btn-outline-dark m-2" to="/events/2020">
            2020
          </NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink class="btn btn-outline-dark m-2" to="/events/2021">
            2021
          </NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink class="btn btn-outline-dark m-2" to="/events/2022">
            2022
          </NuxtLink>
        </li>
    </ul>
    </div>  
  </template>
  
  <script>
  // Components JS Scripts would go here
  </script>