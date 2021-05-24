<template>
<section>
    <div v-if="loading">Loading...</div>

  <div class='profileBox'
  v-for="profile in profiles"
      :key="profile.first"
      data-aos="zoom-in"
       data-aos-delay="1000"
  >
      <div class="profile-avatar" >
        <img :src="profile.picture.large" alt='profile.gender'/>
      </div>
      <div class="profile-details">
        <h2 >
          {{ profile.name.first }}
          {{ profile.name.last }}
        </h2>
        <ul>
           <li><strong>Phone No:</strong> {{profile.gender }}</li>
          <li><strong>Phone No:</strong> {{profile.phone }}</li>
          <li><strong>Location:</strong> {{ profile.location.city }}, {{ profile.location.state }}</li>
        </ul>
      </div>
    
  </div>
 
    <div v-if="errored">
     <p>We're sorry, we're not able to retrieve this information at the moment, please try back later</p>
  </div>

 </section>
  
</template>

<script>
import axios from "axios";

export default {
  name: 'UserProfiles',
   data () {
    return {
      profiles : [],
      loading: true,
      errored: false
    }
   },
     mounted () {
    axios
     axios.get(`https://randomuser.me/api/?results=10`)
     .then((response) => {
        this.profiles = response.data.results;
      })
      .catch(error => {
        console.log(error)
        this.errored = true
      })
      .finally(() => this.loading = false)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
section{
  margin: 20px auto;
  color: white;
}


li{
  list-style: none;
}

.profileBox{
   width:500px;
  background-color: white;
  color: black;
  margin: 1em auto;
  border:3px solid #8d9d6e;
}

.profile-avatar{
    padding: 1em;
}

.profile-avatar img{
  display: block;
    margin:20px auto;
    border-radius: 50%;
} 
.profile-details{
  padding:10px;
}
.profile-details h2{
  text-align:center;
}

@media screen and (max-width: 500px) {
.profileBox{
   width:250px;
 
}
}


</style>
