<template>
  <div class="container-fluid">
    <table class="table table-responsive-md">
      <thead>
        <tr>
          <th scope="col">Weight in Lbs.</th>
          <th scope="col">Date</th>
          <th scope="col">Edit</th>
        </tr>
        <tr v-for="weightLog in this.weightLogs">
          <td>{{ weightLog.text }}</td>
          <td>{{ weightLog.date }}</td>
          <td><a @click.prevent="weightLogs.splice(weightLogs.indexOf(weightLog), 1)"
                class="delete"
                href="#">Delete</a></td>
        </tr>
      </thead>
    </table>  
  </div>
</template>
<script>

export default {
  name: 'WeightLogList',
  props: ['weightLogs', 'weightLogListKey']
}
</script>
<style>
table {
  margin-top: 5px;
  color: black;
  background-color: #DCDCDC;
  border-top: 1px solid;
}

.delete {
  color: red;
}
td, th {
  border: 1px solid;
}
tr:nth-child(even) {background-color: #F5F5F5;}
</style>
