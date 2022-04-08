<template>
  <div class="announcement mb-4">
    <div class="row">
      <div class="col-md-4 d-flex justify-content-center">
        <img
          class="img-fluid"
          :src="require('@/assets/img/' + announcement.image)"
          alt="imagine"
        />
      </div>
      <div class="col-md-8 justify-content-xs-center">
        <h2 class="title text-justify text-truncate">
          <router-link :to="{ path: '/announcement/' + announcement.id }">
            {{ announcement.title }}
          </router-link>
        </h2>
        <p class="text-justify crop-text-3">
          {{ announcement.description }}
        </p>
        <p class="price">
          {{ announcement.price }}
          <span>EUR</span>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Announcement",
  props: ["announcement"],
};
</script>

<style scoped>
img {
  height: 220px;
  width: 90%;
  object-fit: cover;
}

.crop-text-3 {
  -webkit-line-clamp: 3;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-box-orient: vertical;
}

p {
  margin: 1rem 0;
}

.price {
  font-size: 26px;
  color: green;
}
.price span {
  font-size: 20px;
  vertical-align: top;
}

.announcement {
  padding: 0.5rem;
  background-color: #f9f9f9;
  border: 1px solid #dee2e6;
}

img:hover {
  cursor: pointer;
}

.title:hover {
  cursor: pointer;
  text-decoration: underline;
}
</style>
