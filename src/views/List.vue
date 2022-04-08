<template>
  <div class="list">
    <div class="container">
      <header>
          <h2>
              Toate anunturile
          </h2>
          <hr>
      </header>
      <Announcement
        v-for="announcement in announcements"
        :key="announcement.id"
        v-bind:announcement="announcement"
      />
      <div class="row">
        <nav aria-label="Page navigation example d-flex justify-content-center">
          <ul class="pagination">
            <li class="page-item">
              <a class="page-link" href="#" aria-label="Previous">
                <span aria-hidden="true">&laquo;</span>
              </a>
            </li>
            <li class="page-item active"><a class="page-link" href="#">1</a></li>
            <li class="page-item"><a class="page-link" href="#">2</a></li>
            <li class="page-item"><a class="page-link" href="#">3</a></li>
            <li class="page-item">
              <a class="page-link" href="#" aria-label="Next">
                <span aria-hidden="true">&raquo;</span>
              </a>
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </div>
</template>

<script>
import Announcement from "@/components/Announcement.vue";
import DataService from "@/services/DataService.js";

export default {
  name: "List",
  components: {
    Announcement,
  },
  data() {
    return {
      announcements: [],
    };
  },
    mounted() {
    DataService.getAll().then((response) => {
      this.announcements = response.data;
    });
  },
};
</script>

<style scoped>
h2 {
    margin-top: 100px;
}
</style>
