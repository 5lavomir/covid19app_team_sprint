<template>
  <!--Setting up a table for the information to be displayed -Andrew -->
    <table class="table table-striped table-bordered">
        <thead class="thead-dark">
            <tr>
                <th>Total Worldwide Cases</th>
                <th>Total Worldwide Deaths</th>
                <th>Total Worldwide Recovered</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <!-- There is no script in this component Andy, that is why - "Alex" -->
                <td><!--Doesn't work {{ casesOnCountry.confirmed }}--></td>
                <td><!--{{ casesOnCountry.deaths }}--></td>
                <td><!--{{ casesOnCountry.recovered }}--></td>
            </tr>
        </tbody>
    </table>
</template>

<style>
.table{
  background-color: rgb(114, 141, 150);
  width: 70%;
  margin-left: 15%;
  margin-top: 15px;
}

tbody{
  color: white;
}

th, td {
  text-align: center;
  font-size: 25px;
}
</style>
