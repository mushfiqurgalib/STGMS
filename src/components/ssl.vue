<template>
  <div>

    <Nav> </Nav>
    <!-- Navbar-->

    <div class="container">
      <div class="row py-5 mt-0">
        <!-- For Demo Purpose -->
        <div class="col-md-5 pr-lg-12 mb-6 mb-md-10 col">
          <img
            src="../assets/winnn.jpg"
            alt=""
            class="img-fluid col-md-50 d-none d-md-block"
          />
        
        </div>

        <!-- Registeration Form -->

        <div class="col-md-5 col-lg-5 ml-auto" style="padding-top: 15%">
      
            <div class="row">
    

            </div>

            <div  style="padding-right: 130px" >
                  <div
                class="container-login100-form-btn"
                style="padding-top: 10px"
              >
                <button class="button" ><a href="http://localhost/SSL/example_hosted.php" style="color:white"> SSL Commerz  </a></button>
              </div>
            </div>



          

        </div>
      </div>
    </div>
  </div>
</template>

<script>

import Nav from "./Nav";

export default {
  name: "Register",


  components: {
    Nav,
  }
}
 </script>

<style scoped>
/*
*
* ==========================================
* CUSTOM UTIL CLASSES
* ==========================================
*
*/

.container {
  padding-top: 95px;
}
.border-md {
  border-width: 2px;
}

.btn-facebook {
  background: #405d9d;
  border: none;
}

.btn-facebook:hover,
.btn-facebook:focus {
  background: #314879;
}

.btn-twitter {
  background: #42aeec;
  border: none;
}

.btn-twitter:hover,
.btn-twitter:focus {
  background: #1799e4;
}

/*
*
* ==========================================
* FOR DEMO PURPOSES
* ==========================================
*
*/
/* 
body {
  min-height: 100vh;
} */

.form-control:not(select) {
  padding: 1.5rem 0.5rem;
}

select.form-control {
  height: 52px;
  padding-left: 0.5rem;
}

.form-control::placeholder {
  color: #ccc;
  font-weight: bold;
  font-size: 0.9rem;
}
.form-control:focus {
  box-shadow: none;
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
