<template>
  <div class="home">
    <header class="masthead">
      <div class="container position-relative px-4 px-lg-5">
        <div class="row gx-4 gx-lg-5 justify-content-center">
          <div class="col-md-10 col-lg-8 col-xl-7">
            <div class="site-heading">
              <h2>Tery Automobile</h2>
              <span class="subheading">Un loc mai bun pentru masina ta</span>
            </div>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <Announcement
        v-for="announcement in announcements"
        :key="announcement.id"
        v-bind:announcement="announcement"
      />
      <router-link to="/list" class="d-flex justify-content-end nav-link px-lg-3 py-3 py-lg-4"
        ><h3>
          Vezi toata lista cu anunturi >>
          </h3></router-link
      >
    </div>
  </div>
</template>

<script>
import Announcement from "@/components/Announcement.vue";

export default {
  name: "Home",
  components: {
    Announcement,
  },
  data() {
    return {
      announcements: [
        {
          id: 1,
          title: "BMW  Seria 3",
          description:
            "BMW G20 este un automobil revoluţionar în materie de tehnologie. Cu cea de-a şaptea generaţie, BMW Seria 3 obţine echilibrul perfect între cea mai bună protecţie cu putinţă, utilizarea inovatoare şi plăcerea de a conduce sportiv. În vara anului 2019, BMW Seria 3 Touring, cunoscut pe plan intern sub denumirea G21, a continuat tradiţia break-urilor sportive BMW din clasa medie. Pentru prima dată, un model BMW hibrid este disponibil şi în versiunea Touring: BMW 330e are o autonomie electrică de până la 65 km cu bateria încărcată complet.",
          price: "30000",
          image: "bmw-seria3.jpg",
        },
        {
          id: 2,
          title: "Audi A7",
          description:
            "Audi A7 Sportback este situat între modelele A6 și A8, acesta având ca concurenți modelele Mercedes-Benz CLS și BMW Seria 5 GT.",
          price: "65000",
          image: "audi-a7.jpg",
        },
      ],
    };
  }
};
</script>

<style scoped>
.masthead {
  background-image: url("../assets/img/home-bg.jpg");
}

.announcement img {
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

.announcement img:hover {
  cursor: pointer;
}

.title:hover {
  cursor: pointer;
  text-decoration: underline;
}
</style>
