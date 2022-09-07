<!-- this component can hold site navigation -->
<!-- if we put it here we can avoid having to repeat the code -->
<template>
  <div class="container-fluid">
    <ul class="siteNav nav nav-tabs justify-content-end">
      <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/">
            Home
          </NuxtLink>
      </li>
      <!-- <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/support">
          Support
        </NuxtLink>
      </li> -->
      <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/about">
          About
        </NuxtLink>
      </li>
      <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/events">
          Events
        </NuxtLink>
      </li>
      <!-- <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/learn">
          Learn
        </NuxtLink>
      </li> -->
      <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/links">
          Links
        </NuxtLink>
      </li>
      <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/partners">
          Partners
        </NuxtLink>
      </li>
      <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/buildings">
          Canberra's Modern
        </NuxtLink>    
    </li>
      <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/videos">
          Videos
        </NuxtLink>
      </li>
    </ul>
  </div>  
</template>

<script>
// Components JS Scripts would go here
</script>