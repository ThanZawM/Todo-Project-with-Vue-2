<template>
  <div class="add-new">
    <hr />
    <br />
    <h1>Add New ToDo</h1>
    <hr />
    <br />

    <div class="card" style="width: 36rem">
      <ul class="list-group list-group-flush">
        <li class="list-group-item">
          <div class="mb-3">
            <label for="" class="form-label">Title</label>
            <input
              type="text"
              class="form-control"
              id=""
              placeholder=""
              v-model="title"
            />
          </div>
        </li>
        <li class="list-group-item">
          <div class="mb-3">
            <label for="" class="form-label">Description</label>
            <textarea
              v-model="description"
              class="form-control"
              id=""
              rows="3"
            ></textarea>
          </div>
        </li>
      </ul>
      <div class="card-footer">
        <button type="button" class="btn btn-success" @click="onSubmit">
          Save
        </button>
      </div>
    </div>

    <br /><br />
    <div>
      <h1>All ToDos</h1>
      <!-- <List v-for="item in items" :item="item" :key="item" ></List> -->
      <!-- <List v-for="item in items" :item="item" :key="item.ID"></List> -->
      <br />
      <!-- <table calss="table table-hover ">
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
          <tr v-for="item in items" :key="item.ID">
            <td>{{ item.ID }}</td>
            <td>{{ item.title }}</td>
            <td>{{ item.description }}</td>
            <td><button @click="editRow(item)">Edit</button></td>
            <td><button @click="deleteRow(item)">Delete</button></td>
          </tr>
        </tbody>
      </table> -->

      <List :items="items"></List>
    </div>
  </div>
</template>

<script>
import List from "../components/List.vue";

export default {
  name: "AddNewView",
  components: { List },
  data() {
    return {
      ID: 1,
      title: "",
      description: "",
      items: [],
      edit: false,
      editID: 0,
    };
  },
  methods: {
    onSubmit() {
      var newItem = new Object();
      newItem.ID = this.ID;
      newItem.title = this.title;
      newItem.description = this.description;

      // For Adding new todo
      if (!this.edit) {
        this.ID++;
        // var newItem = new Object();
        // newItem.ID = this.ID++;
        // newItem.title = this.title;
        // newItem.description = this.description;
        this.items.push(newItem);
        this.title = "";
        this.description = "";
        console.log("added new todo")
      } 
      // For Editing todo
      else { 
        console.log("Edit " + this.edit);
        console.log(newItem.ID);
        console.log(this.editID);
        this.items[this.editID].title = newItem.title;
        this.items[this.editID].description = newItem.description; 
        this.title = "";
        this.description = "";
        this.edit = false;
      }
    },

    editRow(item) {
      this.edit = true;
      var id = item.ID - 1;
      this.editID = id;
      console.log("edit ID " + id);
      this.title = this.items[id].title;
      this.description = this.items[id].description;
    },

    deleteRow(item) {
      console.log("delete ID " + item.ID);
      this.items = this.items.filter((f) => f.ID != item.ID);
      // console.log(this.items);
    },
  },
};
</script>

<style scoped>
.card {
  margin: auto;
}
hr {
  width: 50%;
  margin: auto;
}

@import "~bootstrap/dist/css/bootstrap.css";
</style>
