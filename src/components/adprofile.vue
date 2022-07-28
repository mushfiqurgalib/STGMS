<template>
  <div>
    <Nav></Nav>
    <section class="bg-light" v-for="inf in info" :key="inf.id">
      <div class="container">
        <div class="row">
          <div class="col-lg-12 mb-4 mb-sm-5">
            <div class="card card-style1 border-0">
              <div class="card-body p-1-9 p-sm-2-3 p-md-6 p-lg-7">
                <div class="row align-items-center">
                  <div class="col-lg-6 mb-4 mb-lg-0">
                    <img
                      src="https://bootdey.com/img/Content/avatar/avatar7.png"
                      alt="..."
                    />
                  </div>
                  <div class="col-lg-6 px-xl-10">
                    <div
                      class="bg-secondary d-lg-inline-block py-1-9 px-1-9 px-sm-6 mb-1-9 rounded"
                    >
                      <h3 class="h2 text-white mb-0">Name: {{ inf.name }}</h3>
                      <span class="text-primary">Employee</span>
                    </div>
                    <ul class="list-unstyled mb-1-9">

                        <li class="mb-2 mb-xl-3 display-28 text-white">
                          <h3>  
                         
                          ADMIN ID :
                    
                   {{ inf.id }} </h3>
                      </li>



                
                      <li class="mb-2 mb-xl-3 display-28 text-white">
                          <h3>  
                         
                          Mobile :
                    
                   {{ inf.mobile }} </h3>
                      </li>


                      <li class="mb-2 mb-xl-3 display-28 text-white">
                      <h3>    
                          Email:
                        
                      bsse11@iit.du.ac.bd </h3>
                  
                      </li>
                      <li class="mb-2 mb-xl-3 display-28 text-white">
                     <h3> Website : www.sultantea.com </h3>
                      </li>
                      
                    </ul>
     
                  </div>
                </div>
              </div>
            </div>
          </div>
   
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import axios from "axios";
import Nav from "./Nav.vue";

export default {
  name: "profilepage",
  components:{
    Nav
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
      axios
        .post("/viewprofile.php", {
          id: localStorage.getItem("id"),
        })
        .then((response) => (this.info = response.data));
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
  background-color: #fff;
  background-clip: border-box;
  border: 0px solid rgba(0, 0, 0, 0);
  border-radius: 0.25rem;
  margin-bottom: 1.5rem;
  box-shadow: 0 2px 6px 0 rgb(218 218 253 / 65%),
    0 2px 6px 0 rgb(206 206 238 / 54%);
}
/* 
element.style {
}
.list-inline-item:not(:last-child) {
  margin-right: 0.5rem;
} */
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
  background-color: #f4f4f4 !important;
}

/* CSSSSSSSSSSSSSSSSSSSSSSSSSSSSS */

body {
  margin-top: 20px;
}
.card-style1 {
  box-shadow: 0px 0px 10px 0px rgb(89 75 128 / 9%);
}
.border-0 {
  border: 0 !important;
}
.card {
  position: relative;
  display: flex;
  flex-direction: column;
  min-width: 0;
  word-wrap: break-word;
  background-color: #175e4f;
  background-clip: border-box;
  border: 1px solid rgba(0, 0, 0, 0.125);
  border-radius: 0.25rem;
}

section {
  padding: 120px 0;
  overflow: hidden;
  background: rgb(17, 17, 17);
}
.mb-2-3,
.my-2-3 {
  margin-bottom: 2.3rem;
}

.section-title {
  font-weight: 600;
  letter-spacing: 2px;
  text-transform: uppercase;
  margin-bottom: 10px;
  position: relative;
  display: inline-block;
}
.text-primary {
  color: #ceaa4d !important;
}
.text-secondary {
  color: #15395a !important;
}
.font-weight-600 {
  font-weight: 600;
}
.display-26 {
  font-size: 1.3rem;
}

@media screen and (min-width: 992px) {
  .p-lg-7 {
    padding: 4rem;
  }
}
@media screen and (min-width: 768px) {
  .p-md-6 {
    padding: 3.5rem;
  }
}
@media screen and (min-width: 576px) {
  .p-sm-2-3 {
    padding: 2.3rem;
  }
}
.p-1-9 {
  padding: 1.9rem;
}

.bg-secondary {
  background: #15395a !important;
}
@media screen and (min-width: 576px) {
  .pe-sm-6,
  .px-sm-6 {
    padding-right: 3.5rem;
  }
}
@media screen and (min-width: 576px) {
  .ps-sm-6,
  .px-sm-6 {
    padding-left: 3.5rem;
  }
}
.pe-1-9,
.px-1-9 {
  padding-right: 1.9rem;
}
.ps-1-9,
.px-1-9 {
  padding-left: 1.9rem;
}
.pb-1-9,
.py-1-9 {
  padding-bottom: 1.9rem;
}
.pt-1-9,
.py-1-9 {
  padding-top: 1.9rem;
}
.mb-1-9,
.my-1-9 {
  margin-bottom: 1.9rem;
}
@media (min-width: 992px) {
  .d-lg-inline-block {
    display: inline-block !important;
  }
}
.rounded {
  border-radius: 0.25rem !important;
}
</style>
