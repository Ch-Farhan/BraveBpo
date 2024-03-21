<template>
  <div>
    <div v-if="loading">Loading...</div>
    <div v-else>
      <div v-for="result in results" :key="result.login.uuid">
        <div class="container d-flex justify-content-center align-items-center">             
             <div class="card">
              <div class="upper">
                <img src="../assets/Untitled.jpg" class="img-fluid">
              </div>
              <div class="user text-center">
                <div class="profile">
                  <img style="border-radius: 50px;" :src="result.picture.thumbnail" :alt="result.name.first">
                </div>
              </div>
              <div class="mt-5 text-center">
                <span class="text-muted d-block mb-2">Hi, My name is</span>
                <h4 class="mb-0"><p>{{ result.name.title }} {{ result.name.first }} {{ result.name.last }}</p></h4>
                <div class="d-flex justify-content-between align-items-center mt-4 px-4">
                  <div class="stats">
                    <hr>
                    <span><a href=""><i class="fa fa-user" style="color: green; font-size: 54px;" aria-hidden="true"></i></a></span>
                  </div>

                  <div class="stats">
                    <span><a href=""><i class="fa fa-envelope" style="color: green; font-size: 54px;" aria-hidden="true"></i></a></span>
                  </div>

                  <div class="stats">
                    <span><a href=""><i class="fa fa-file" style="color: green; font-size: 54px;" aria-hidden="true"></i></a></span>
                  </div>

                  <div class="stats">
                    <span><a href=""><i class="fa fa-map-marker" style="color: green; font-size: 54px;" aria-hidden="true"></i></a></span>
                  </div>

                  <div class="stats">
                    <span><a href=""><i class="fa fa-phone" style="color: green; font-size: 54px;" aria-hidden="true"></i></a></span>
                  </div>
                  <div class="stats">
                    <span><a href=""><i class="fa fa-briefcase" style="color: green; font-size: 54px;" aria-hidden="true"></i></a></span>
                  </div>
                </div>
              </div>
             </div>
           </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      loading: true,
      results: [],
      info: {}
    };
  },
  created() {
    this.fetchresultData();
  },
  methods: {
    fetchresultData() {
      axios.get('https://randomuser.me/api/')
        .then(response => {
          this.loading = false;
          this.results = response.data.results;
          // info data
          // this.info = response.data.info;
        })
        .catch(error => {
          console.error('Uh oh, something has gone wrong. Please tweet us @randomapi about the issue. Thank you.', error);
        });
    }
  },
}

$(document).ready(function(){
      $("#myInput").on("keyup", function() {
        var value = $(this).val().toLowerCase();
        $("#myTable tr").filter(function() {
          $(this).toggle($(this).text().toLowerCase().indexOf(value) > -1)
        });
      });
    });
</script>
    <script>

    </script>
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:weight@100;200;300;400;500;600;700;800&display=swap");


body{
 background-color:#545454;
 font-family: "Poppins", sans-serif;
 font-weight: 300;
}

.container{
 height: 100vh;
}

.card{

 width: 980px;
 border: none;
 border-radius: 15px;
 padding: 8px;
 background-color: #fff;
 position: relative;
 height: 370px;
}

.upper{

 height: 100px;

}

.upper img{
 height: 250px;
 width: 1080px;
 border-top-left-radius: 10px;
 border-top-right-radius: 10px;
margin-top: -50px;
}

.user{
  margin-top: 100px;

 position: relative;
}

.profile img{ 
 height: 80px;
 width: 80px;
 margin-top:3px;
 margin-left:-1px;
}

.profile{

 position: absolute;
 top:-50px;
 left: 46%;
 height: 90px;
 width: 90px;
 border:3px solid #fff;

 border-radius: 50%;

}

.follow{

 border-radius: 15px;
 padding-left: 20px;
 padding-right: 20px;
 height: 35px;
}

.stats span{

 font-size: 29px;
}
</style>
