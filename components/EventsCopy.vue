<!-- this component can hold site navigation -->
<!-- if we put it here we can avoid having to repeat the code -->
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
    <p> The year is currently {{currentYear}}</p>

		<!-- these would show while the data loads or if an error -->
		<p v-if="$fetchState.pending"> <span class="loading"></span></p>
		<p v-else-if="$fetchState.error">Error while fetching events</p>

		<ul v-else class="list-group">
			<!-- this is a for loop, it just loops through the list of buildings returned from the API -->
			<li v-for="event in events" :key="event.id" class="list-group-item">
				<!-- now make a link for each item -->
				<!-- <NuxtLink :to="building.slug"> -->
				<NuxtLink :to="'/events/' + event.slug">
					<!-- return the rendered title -->
					{{  event.title.rendered  }}
				</NuxtLink>
				<!-- now show me the building year -->
				: {{ event.acf.year }}
			</li>
		</ul>
  
    </div>  
  </template>

<script>
export default {
		data() {
		return {
     //empty array to be filled with all events
			events: [],
      arr2017:[],
      arr2018:[],
      arr2019:[],
      arr2020:[],
      arr2021:[],
      arr2022:[],
    
      //Unless changed by methods, will show events for current year #FutureProofing... kinda, still need to add a new method and button for future years...
      currentYear: new Date().getFullYear(),
      year: new Date().getFullYear(),
     
      //Variables to that hold years to filter by - may try to change to an array before submission, if not or i forget to delete this - Hi Ben :)
			yearList:['2017','2018','2019','2020','2021','2022','2023'],
		}
	},

	//now go get the data
	async fetch() {
		//make the api call and fill the empty events array
		let apiData = await fetch('http://cm.beneb.com/wp-json/wp/v2/events/?per_page=100')
		.then((response) =>
			response.json()
		)
    this.events = apiData;
	// 	console.log(apiData)
	// 	// // create empty araay
	// 	let yearArr = [];
	// 	//loop through buildings/events array
	// 	for (let i = 0; i < apiData.length; i++) {
	// 		// some variables
	// 		let eventYear = apiData[i].acf.year;
	// 		// for each one, check the year
	// 			if (eventYear == this.year) {
	// 				//if there's a match, push into new array
	// 					yearArr.push(apiData[i]);
	// 			}
	// 	} 
	// 	console.log(yearArr);
	// 	//now set buildings to be the yearArray 
	// 	this.events = yearArr;
	},

  methods: {
    event2017(event) {
        // `this` inside methods points to the current active instance
        this.year = this.yearList[0];
        // `event` is the native DOM event
        if (event) {
          for (let i = 0; i < this.events.length; i++) {
            // some variables
            let eventYear = this.events[i].acf.year;
            // for each one, check the year
            if (eventYear == this.year) {
              //if there's a match, push into new array
                this.arr2017.push(this.events[i]);
              }
          }
        }
        this.events = this.arr2017;
        console.log(this.events)
        console.log(this.arr2017)
      },
      event2018(event) {
        // `this` inside methods points to the current active instance
        this.year = this.yearList[1];
        // `event` is the native DOM event
        if (event) {
          for (let i = 0; i < this.events.length; i++) {
            // some variables

            let eventYear = this.events[i].acf.year;
            // for each one, check the year
            if (eventYear == this.year) {
              //if there's a match, push into new array
                this.arr2018.push(this.events[i]);
              }
          }
        }
        this.events = this.arr2018;
      },
  event2019(event) {
    // `this` inside methods points to the current active instance
    this.year = this.yearList[2];
    // `event` is the native DOM event
    if (event) {
      console.log(this.year)
    }
  },
  event2020(event) {
    // `this` inside methods points to the current active instance
    this.year = this.yearList[3];
    // `event` is the native DOM event
    if (event) {
      console.log(this.year)
    }
  },
  event2021(event) {
    // `this` inside methods points to the current active instance
    this.year = this.yearList[4];
    // `event` is the native DOM event
    if (event) {
      console.log(this.year)
    }
  },
  event2022(event) {
    // `this` inside methods points to the current active instance
    this.year = this.yearList[5];
    // `event` is the native DOM event
    if (event) {
      console.log(this.year)
    }
  }
},
}
</script>



<!-- this component can hold site navigation -->
<!-- if we put it here we can avoid having to repeat the code -->
<!-- <template>
  <div class="container-fluid">
    <ul class="nav nav-tabs justify-content-end">
      <li class="nav-item">
        <NuxtLink class="btn btn-outline-dark m-2" to="/events">
            Events
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
  </ul>
  </div>  
</template> -->