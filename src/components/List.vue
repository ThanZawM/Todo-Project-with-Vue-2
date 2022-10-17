<template>
  <div>
    <!-- <div>
      <p>TITLE</p>
      <p>{{ item.title }}</p>
    </div>
    <div>
      <p>DESCRIPTION</p>
      <p>{{ item.description }}</p>
    </div> -->
    <table calss="table table-hover ">
        <thead>
          <tr>
            <th>No</th>
            <th>Title</th>
            <th>Description</th>
            <th>Edit</th>
            <th>Delete</th>
          </tr>
        </thead>
        <tbody>
          <!-- <tr v-for="item in items" :key="item.ID"> -->
        <tr v-for="item in items" :key="item.ID">
            <td>{{ item.ID }}</td>
            <td>{{ item.title }}</td>
            <td>{{ item.description }}</td>
            <td><button @click="editRow(item)">Edit</button></td>
            <td><button @click="deleteRow(item)">Delete</button></td>
          </tr>
        </tbody>
      </table>
  </div>
</template>

<script>
export default {
  props: ["items"],
};
</script>

<style>
@import "~bootstrap/dist/css/bootstrap.css";
</style>
