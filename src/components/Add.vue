<template>
  <div>
    <div class="card" style="width: 36rem">
      <ul class="list-group list-group-flush">
        <li class="list-group-item">
          <div class="mb-3">
            <label for="" class="form-label">TITLE</label>
            <input
              type="text"
              class="form-control"
              id=""
              placeholder=""
              v-model="title"
            />
          </div>
        </li>
        <!-- <li class="list-group-item">
          <p>Title is {{ title }}</p>
        </li> -->
        <li class="list-group-item">
          <div class="mb-3">
            <label for="" class="form-label">DESCRIPTION</label>
            <textarea
              v-model="description"
              class="form-control"
              id=""
              rows="3"
            ></textarea>
          </div>
        </li>
        <!-- <li class="list-group-item">
          <p>Description is {{ description }}</p>
        </li> -->
      </ul>
      <div class="card-footer">
        <button type="button" class="btn btn-success" @click="onSubmit">
          Save
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name:"Add"
}
</script>

<style>

@import "~bootstrap/dist/css/bootstrap.css";
</style>