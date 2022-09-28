

<template>
  <div>
    <nav3></nav3>

   
    <header class="header">
      <nav class="navbar navbar-expand-lg navbar-light py-3">
        <div class="container">
          <!-- Navbar Brand -->
          <a href="#" class="navbar-brand">
            <img src="../assets/logo-3.png" alt="logo" width="120" />
          </a>
        </div>
      </nav>
    </header>

    <div class="container">
      <div class="row py-5 mt-4 align-items-center">
        <!-- For Demo Purpose -->
        <div class="col-md-5 pr-lg-5 mb-5 mb-md-0">
          <img
            src="../assets/apply.jpg"
            alt=""
            class="img-fluid mb-3 d-none d-md-block"
          />
          <h1>Apply for loan</h1>
        </div>

        <!-- Registeration Form -->
        <div class="col-md-7 col-lg-6 ml-auto bg" >
          <form @submit.prevent="handleSubmit" style="position: center">
            <div class="row">
              <!-- ID-->
              <div class="input-group col-lg-8 mb-4">
                <div class="input-group-prepend">
                  <span
                    class="input-group-text bg-white px-4 border-md border-right-0"
                  >
                    <i class="fa fa-user text-muted"></i>
                  </span>
                </div>
                <input
                  id="Name"
                  style="font-weight:bold;"
                  type="text"
                  name="firstname"
                  v-model="employeeid"
                  placeholder="Employee ID"
                  class="form-control bg-white border-left-0 border-md"
                />
              </div>

              <!--  Name -->
              <div class="input-group col-lg-8 mb-4">
                <div class="input-group-prepend">
                  <span
                    class="input-group-text bg-white px-4 border-md border-right-0"
                  >
                    <i class="fa fa-user text-muted"></i>
                  </span>
                </div>
                <input
                 style="font-weight:bold;"
                  id="firstName"
                  type="text"
                  name="firstname"
                  v-model="ename"
                  placeholder=" Full Name"
                  class="form-control bg-white border-left-0 border-md"
                  v-on:change="onChangeFileUpload()"
                />
              </div>

              <!-- Phone Number -->
              <div class="input-group col-lg-8 mb-4">
                <div class="input-group-prepend">
                  <span
                    class="input-group-text bg-white px-4 border-md border-right-0"
                  >
                    <i class="fa fa-phone-square text-muted"></i>
                  </span>
                </div>

                <input
                  id="phoneNumber"
                   style="font-weight:bold;"
                  type="text"
                  name="phone"
                  v-model="mobile"
                  placeholder="Mobile Number"
                  class="form-control bg-white border-md border-left-0 pl-3"
                />
              </div>

              <div class="input-group col-lg-8 mb-4">
                <div class="input-group-prepend">
                  <span
                    class="input-group-text bg-white px-4 border-md border-right-0"
                  >
                    <i class="fa fa fa-file text-muted"></i>
                  </span>
                </div>

                <!-- <input
                  id="file"
                  type="file"
                  name="file"
                  ref="file"
                  v-on:change="onChangeFileUpload()"
                  placeholder="File"
                  class="form-control bg-white border-md border-left-0 pl-3"
                /> -->

                <input
                 style="font-weight:bold;"
                 
                  type="file"
                  id="file"
                  ref="file"
                  v-on:change="onChangeFileUpload()"
                />
              </div>

       
<!-- 
              <button style="font-weight: bold " v-on:click="submitForm()" >
                Upload
              </button> -->


             <div
               
               class="col-md-7 col-lg-6 "
              >
                <button  v-on:click="submitForm()" class="button">Upload </button>

                <!-- <a href="#" class="button">Link Button</a> -->
              </div>


              <!-- Already Registered -->
            </div>
          </form>

        </div>
      </div>
    </div>
  </div>
</template>








<script>
import axios from "axios";
import nav3 from "./nav3";
export default {
  name: "FileUp",
  components: {
    nav3,
  },
  data() {
    return {
      employeeid: "",
      ename: "",
      mobile: "",
      file: "",
    };
  },

  methods: {
    submitForm() {
      let formData = new FormData();
      formData.append("myfile", this.file);
      formData.append("employeeid", this.employeeid);
      formData.append("ename", this.ename);
      formData.append("mobile", this.mobile);

      axios
        .post("fileslogic.php", formData, {
          headers: {
            "Content-Type": "multipart/form-data",
          },
        })
        .then(function (data) {
          console.log(data);
          console.log("Hello world");
        })
        .catch(function () {
          console.log("FAILURE!!");
        });

      
      
  this.$router.push("/home3");

      // if (response.data[0].status == 1) {
      //   alert("File upload successfully!");
      //   this.$router.push("/home3");
      // } else {
      //   alert("Failed!!");
      // }
    },

    onChangeFileUpload() {
      this.file = this.$refs.file.files[0];
    },
  },
};
</script>

<style scoped>

/*
html {
  height: 100%;
}
body {
  margin: 0;
  padding: 0;
  font-family: sans-serif;
  background: linear-gradient(#2b6e3c, #f1f3f2);
}
 
.login-box {
  position: absolute;
  top: 50%;
  left: 50%;
  height: 450px;
  width: 850px;
  padding: 40px;
  transform: translate(-50%, -50%);

  background: rgb(52, 123, 131);

  border-radius: 10px;
}

.login-box h2 {
  margin: 0 0 30px;
  padding: 0;
  color: #161817;
  text-align: center;
}

.login-box .user-box {
  position: relative;
}

.login-box .user-box input {
  width: 100%;
  padding: 10px 0;
  font-size: 16px;
  color: rgb(11, 11, 11);
  margin-bottom: 30px;
  border: none;
  border-bottom: 1px solid rgb(230, 229, 229);
  outline: none;
  background: transparent;
  font-weight: bold;
}
.login-box .user-box label {
  position: absolute;
  top: 0;
  left: 0;
  padding: 10px 0;
  font-size: 16px;
  color: rgb(0, 0, 0);
  pointer-events: none;
  transition: 0.5s;
  font-weight: bold;
}

.login-box .user-box input:focus ~ label,
.login-box .user-box input:valid ~ label {
  top: -20px;
  left: 0;
  color: #0b0b0b;
  font-size: 12px;
  font-weight: bold;
}

.login-box form a {
  position: relative;
  display: inline-block;
  padding: 10px 20px;
  color: #03e9f4;
  font-size: 16px;
  text-decoration: none;
  text-transform: uppercase;
  overflow: hidden;
  transition: 0.5s;
  margin-top: 40px;
  letter-spacing: 4px;
}

.login-box a:hover {
  background: #103537;
  color: rgb(7, 7, 7);
  border-radius: 5px;
  box-shadow: 0 0 5px #03484c, 0 0 25px #03e9f4, 0 0 50px #03e9f4,
    0 0 100px #03e9f4;
}

.login-box a span {
  position: absolute;
  display: block;
}

.login-box a span:nth-child(1) {
  top: 0;
  left: -100%;
  width: 100%;
  height: 2px;
  background: linear-gradient(90deg, transparent, #03e9f4);
  animation: btn-anim1 1s linear infinite;
}

@keyframes btn-anim1 {
  0% {
    left: -100%;
  }
  50%,
  100% {
    left: 100%;
  }
}

.login-box a span:nth-child(2) {
  top: -100%;
  right: 0;
  width: 2px;
  height: 100%;
  background: linear-gradient(180deg, transparent, #03e9f4);
  animation: btn-anim2 1s linear infinite;
  animation-delay: 0.25s;
}

@keyframes btn-anim2 {
  0% {
    top: -100%;
  }
  50%,
  100% {
    top: 100%;
  }
}

.login-box a span:nth-child(3) {
  bottom: 0;
  right: -100%;
  width: 100%;
  height: 2px;
  background: linear-gradient(270deg, transparent, #03e9f4);
  animation: btn-anim3 1s linear infinite;
  animation-delay: 0.5s;
}

@keyframes btn-anim3 {
  0% {
    right: -100%;
  }
  50%,
  100% {
    right: 100%;
  }
}

.login-box a span:nth-child(4) {
  bottom: -100%;
  left: 0;
  width: 2px;
  height: 100%;
  background: linear-gradient(360deg, transparent, #03e9f4);
  animation: btn-anim4 1s linear infinite;
  animation-delay: 0.75s;
}

@keyframes btn-anim4 {
  0% {
    bottom: -100%;
  }
  50%,
  100% {
    bottom: 100%;
  }
} */

.header{
  padding-top: 4.5%;
}



</style>
