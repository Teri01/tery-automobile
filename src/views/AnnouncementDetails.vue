<template>
  <div class="announcement-details">
    <div class="container">
      <h1>{{announcement.title}}</h1>
      <img
        class="img-thumbnail"
        :src="require('@/assets/img/' + announcement.image)"
        alt="imagine"
      />
      <p class="price">
        {{announcement.price}}
        <span>EUR</span>
      </p>
      <p class="text-justify">
        {{announcement.description}}
      </p>
    </div>
  </div>
</template>

<script>
import DataService from "@/services/DataService.js";

export default {
  name: "AnnouncementDetails",
  data() {
    return {
      announcement: {
        id: '',
        title: '',
        description: '',
        image: 'default.jpg',
        price: ''
      }
    };
  },
  mounted() {
    DataService.get(this.$route.params.id).then((response) => {
      this.announcement.id = response.data.id;
      this.announcement.title = response.data.title;
      this.announcement.description = response.data.description;
      this.announcement.image = response.data.image;
      this.announcement.price = response.data.price;
    });
  },
};
</script>

<style scoped>
img {
  height: 700px;
  width: 100%;
  object-fit: cover;
  display: flex;
  margin: 0 auto;
}

.announcement-details {
  margin-top: 100px;
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
</style>
