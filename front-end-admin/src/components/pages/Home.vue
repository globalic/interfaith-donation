<template>
  <div>
    <div class="home">
      <!-- Main jumbotron for a primary marketing message or call to action -->
      <div v-if="loggedIn" class="jumbotron">
        <div class="container">
          <div>&nbsp;</div>
          <!--<p>Welcome back, <% out.print(user.getUsername()); %>! </p>-->
          <div class="col-md-6">
            <p><router-link to="register-donor" class="btn btn-default" role="button">Add Donor&raquo;</router-link></p>
            <form class="form-horizontal" action="/searchdonor" method="GET">
              <div class="form-group">
                <label class="control-label col-sm-2">Search:</label>
                <input name="searchterm" type="text" width="50">
                <button type="submit">Search</button>
              </div>
            </form>
            <p><router-link to="donors" >Click here for full donor list</router-link></p>
            <!-- <h3>Recent Donors</h3>
            <table class="table">
              <thead>
              <tr>
                <th>Donor Name</th>
                <th>Email</th>
                <th>Joined On</th>
              </tr>
              </thead>
              <tbody id="topDonorTBody">
              </tbody>
            </table> -->
          </div>
          <div class="col-md-6">
            <p><router-link to="register-need" class="btn btn-default" role="button">Add Need&raquo;</router-link></p>
            <form class="form-horizontal" action="/searchneeds" method="GET">
              <div class="form-group">
                <label class="control-label col-sm-2">Search:</label>
                <input name="searchterm" type="text" width="50">
                <button type="submit">Search</button>
              </div>
            </form>
            <p><router-link to="needs" >Click here for full need list</router-link></p>
            <!-- <h3>Recent Needs</h3>
            <table class="table">
              <thead>
              <tr>
                <th>Need</th>
                <th>Create Date</th>
                <th>Link</th>
              </tr>
              </thead>
              <tbody id="needTBody">
              </tbody>
            </table> -->
          </div>
        </div>
      </div>
      <div v-if="!loggedIn" class="jumbotron">
        <div class="container">
          <h1>ISH Services Inc.</h1>
          <p>Database and web framework for posting and tracking donations and donors</p>
          <p><router-link class="btn btn-primary btn-lg" to="/about" role="button">Learn More &raquo;</router-link></p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'home',
  data() {
    return {
      loggedIn: false
    };
  }
};
</script>

<style scoped>

</style>
