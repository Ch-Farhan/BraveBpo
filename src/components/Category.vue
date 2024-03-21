<template>
  <div>
    <div v-if="loading">Loading...</div>
    <div v-else>
      <div v-for="result in results" :key="result.login.uuid">
        <div class="row">
          <div class="col-3">
            <h1 class="mt-4 ms-3 text-primary border-primary">You can search here</h1>
          </div>

        </div>
        <input class="p-2 mt-2 ms-3" style="width: 340px; height: 50px;" id="myInput" type="text" placeholder="Search..">
        <br>
        <br>

        
        <v-table class="table table-warning ">
<thead>
  <tr class=" table-secondary">
    <th scope="col">Profile</th>
    <th scope="col">Gender</th>
    <th scope="col">Name</th>
    <th scope="col">Location</th>
    <th scope="col">Email</th>
    <th scope="col">Login Username, Password, Salt, md5, sha1, sha256</th>
    <th scope="col">Registered Date, Age</th>
    <th scope="col">Dob Date, Age</th>
    <th scope="col">Phone</th>
    <th scope="col">Cell</th>
    <th scope="col">id name, value</th>
    <th scope="col">Coordinates latitude, longitude</th>
    <th scope="col">Timezone offset, description</th>
    <th scope="col">Picture Large, Medium, Thumbnail</th>
    <th scope="col">Nat</th>
  </tr>
</thead>
<tbody id="myTable">
  <tr>
    <th scope="row">
      <button class="btn btn-outline-primary mt-4 ">
        <RouterLink to="/profile">Profile</RouterLink>
      </button>
    </th>
    <td><p>{{ result.gender }}</p></td>
    <td><p>{{ result.name.title }} {{ result.name.first }} {{ result.name.last }}</p></td>
    <td>{{ result.location.street.number }}, {{ result.location.street.name }}, {{ result.location.city }}, {{ result.location.state }}, {{ result.location.country }}, {{ result.location.postcode }}</td>
    <td>{{ result.email }}</td>
    <td>{{ result.login.uuid }}, {{ result.login. username }}, {{ result.login.password }}, {{ result.login.salt }}, {{ result.login.md5 }}, {{ result.login.sha1 }}, {{ result.login.sha256 }}</td>
    <td>{{ result.registered.date }}, {{ result.registered.age }}</td>
    <td>{{ result.dob.date }}, {{ result.dob.age }}</td>
    <td>{{ result.phone }}</td>
    <td>{{ result.cell }}</td>
    <td>{{ result.id.name }}, {{ result.id.value }}</td>
    <td>{{ result.location.coordinates.latitude }}, {{ result.location.coordinates.longitude }}</td>
    <td>{{ result.location.timezone.offset }}, {{ result.location.timezone.description }}</td>
    <td><img :src="result.picture.large" :alt="result.name.first"> , <img :src="result.picture.medium" :alt="result.name.first"> , <img :src="result.picture.thumbnail" :alt="result.name.first"></td>
    <td>{{ result.nat }}</td>
  </tr>
  <tr>
    <th scope="row">
      <button class="btn btn-outline-primary mt-4 ">
        <RouterLink to="/profile">Profile</RouterLink>
      </button>
    </th>
    <td><p>{{ result.gender }}</p></td>
    <td><p>{{ result.name.title }} {{ result.name.first }} {{ result.name.last }}</p></td>
    <td>{{ result.location.street.number }}, {{ result.location.street.name }}, {{ result.location.city }}, {{ result.location.state }}, {{ result.location.country }}, {{ result.location.postcode }}</td>
    <td>{{ result.email }}</td>
    <td>{{ result.login.uuid }}, {{ result.login. username }}, {{ result.login.password }}, {{ result.login.salt }}, {{ result.login.md5 }}, {{ result.login.sha1 }}, {{ result.login.sha256 }}</td>
    <td>{{ result.registered.date }}, {{ result.registered.age }}</td>
    <td>{{ result.dob.date }}, {{ result.dob.age }}</td>
    <td>{{ result.phone }}</td>
    <td>{{ result.cell }}</td>
    <td>{{ result.id.name }}, {{ result.id.value }}</td>
    <td>{{ result.location.coordinates.latitude }}, {{ result.location.coordinates.longitude }}</td>
    <td>{{ result.location.timezone.offset }}, {{ result.location.timezone.description }}</td>
    <td><img :src="result.picture.large" :alt="result.name.first"> , <img :src="result.picture.medium" :alt="result.name.first"> , <img :src="result.picture.thumbnail" :alt="result.name.first"></td>
    <td>{{ result.nat }}</td>
  </tr>
  <tr>
    <th scope="row">
      <button class="btn btn-outline-primary mt-4 ">
        <RouterLink to="/profile">Profile</RouterLink>
      </button>
    </th>
    <td><p>{{ result.gender }}</p></td>
    <td><p>{{ result.name.title }} {{ result.name.first }} {{ result.name.last }}</p></td>
    <td>{{ result.location.street.number }}, {{ result.location.street.name }}, {{ result.location.city }}, {{ result.location.state }}, {{ result.location.country }}, {{ result.location.postcode }}</td>
    <td>{{ result.email }}</td>
    <td>{{ result.login.uuid }}, {{ result.login. username }}, {{ result.login.password }}, {{ result.login.salt }}, {{ result.login.md5 }}, {{ result.login.sha1 }}, {{ result.login.sha256 }}</td>
    <td>{{ result.registered.date }}, {{ result.registered.age }}</td>
    <td>{{ result.dob.date }}, {{ result.dob.age }}</td>
    <td>{{ result.phone }}</td>
    <td>{{ result.cell }}</td>
    <td>{{ result.id.name }}, {{ result.id.value }}</td>
    <td>{{ result.location.coordinates.latitude }}, {{ result.location.coordinates.longitude }}</td>
    <td>{{ result.location.timezone.offset }}, {{ result.location.timezone.description }}</td>
    <td><img :src="result.picture.large" :alt="result.name.first"> , <img :src="result.picture.medium" :alt="result.name.first"> , <img :src="result.picture.thumbnail" :alt="result.name.first"></td>
    <td>{{ result.nat }}</td>
  </tr>
</tbody>
</v-table>
<br>
<v-table class="table table-warning">
<thead>
  <tr class=" table-secondary">
    <th scope="col">id</th>
    <th scope="col">Seed Info</th>
    <th scope="col">Results Info</th>
    <th scope="col">Page Info</th>
    <th scope="col">Version Info</th>
  </tr>
</thead>
<tbody>
  <tr>
    <th scope="row">1</th>
    <td>{{ info.seed }}</td>
    <td>{{ info.results }}</td>
    <td>{{ info.page }}</td>
    <td>{{ info.version }}</td>
  </tr>
</tbody>
</v-table>
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
          this.info = response.data.info; // Corrected property name
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

</style>
