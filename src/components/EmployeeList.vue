<template>
  <div>
    <Nav> </Nav>

    <h1>Employee list</h1>

    <!-- <button>
      <router-link to="/add" class="nav-link fa-1x" id="button">
        Add Employee
      </router-link>
    </button> -->

  <div style="padding-top:70px"  class="container-login100-form-btn">
     <button >
            <router-link to="/add" class="nav-link"> <d> Add Employee </d></router-link>
          </button>
</div>


    <!-- <Profile v-bind:info="info"> </Profile> -->

    <div class="container">
      <div class="row row-cols-1 row-cols-lg-2 row-cols-xl-4">
        <div class="col" v-for="(inf, index) in info" :key="inf.sid">
          <div class="card radius-15">
            <div class="card-body text-center">
              <div class="p-4 border radius-15">
                <img
                  :src="getImageURL(index)"
                  width="110"
                  height="110"
                  class="rounded-circle shadow"
                  alt=""
                />

                <h5 class="mb-0 mt-5">Name: {{ inf.name }}</h5>
                <h5 class="mb-3">Mobile: {{ inf.mobile }}</h5>
               
                <!-- <div class="d-grid"> <router-link to="/profile" class="btn btn-outline-primary radius-15"> Go to Profile </router-link> -->
<button>
                <router-link :to="{ name: 'Profile', params: { inf } }">
                  Visit Profile</router-link
                >
</button>
                <button
                  @click="
                    () => {
                      deleteProfile(inf.id);
                    }
                  "
                >
                  Delete User
                </button>

                <!-- <button @click="deleteProfile(inf.id)">Send</button> -->
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

import Nav from "./Nav";

export default {
  name: "EmployeeList",
  components: {
    Nav,
  },

  data() {
    return {
      info: "",
    };
  },
  mounted() {
    this.fetchInfo();
  },

  methods: {
    fetchInfo() {
      axios.get("/readall.php").then((response) => (this.info = response.data));
    },
    getImageURL(index) {
      return (
        "https://bootdey.com/img/Content/avatar/avatar" + (index + 1) + ".png"
      );
    },

    deleteProfile(id) {
      console.log("hello");
      // return 'http://localhost/php_test/delete.php?id='+ this.inf.id ;
       axios.post("/delete.php?id=" + id).then(this.fetchInfo());
    },
  },
};
</script>

<style scoped>
body {
  background-color: #f7f7ff;
  margin-top: 20px;
}
.radius-15 {
  border-radius: 15px;
}
.card {
  position: relative;
  display: flex;
  flex-direction: column;
  min-width: 0;
  word-wrap: break-word;
  background-color: rgb(125, 178, 183);
  background-clip: border-box;
  border: 0px solid rgba(0, 0, 0, 0);
  border-radius: 0.25rem;
  margin-bottom: 1.5rem;
  box-shadow: 0 2px 6px 0 rgba(8, 8, 8, 0.65),
    0 2px 6px 0 rgba(19, 81, 114, 0.54);
}

element.style {
}
.list-inline-item:not(:last-child) {
  margin-right: 0.5rem;
}
.contacts-social a {
  font-size: 16px;
  width: 36px;
  height: 36px;
  line-height: 36px;
  background: #ffffff;
  border: 1px solid #eeecec;
  text-align: center;
  border-radius: 50%;
  color: #2b2a2a;
}
.bg-facebook {
  background-color: #3b5998 !important;
}
.bg-twitter {
  background-color: #55acee !important;
}
.bg-linkedin {
  background-color: #0976b4 !important;
}

.container {
  padding-top: 50px;
}
#button {
  padding-left: 50px;
  font: bold;
}




.button {
  background-color: #494d49;
  border: none;
  color: white;
  padding: 10px 25px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}

</style>
