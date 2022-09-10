<!-- this component can hold site navigation -->
<!-- if we put it here we can avoid having to repeat the code -->
<template>
    <nav class="navbar navbar-light headWrapper">
      <div class="d-flex justify-content-start">
          <span class="navbar-brand">
            <img src="~assets/images/cmlogo.png" alt="" width="150" height="150" class="d-inline-block align-text-top">
          </span>
          <NuxtLink class="cmlogo siteNav d-inline-block flex-start" to="/">
            Canberra Modern
          </NuxtLink>
      </div>
      <div class= "d-flex navWrapper justify-content-end">
        <ul class= "nav">
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
    </nav>
</template>
<style scoped>
  @import url('~assets/css/style.css');
  @import url('http://fonts.cdnfonts.com/css/futura-std-4');
</style>