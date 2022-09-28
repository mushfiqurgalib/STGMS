<template>
  <div>
    <Nav> </Nav>
    <h1 style="padding-top: 7%">Application List</h1> <br>

    <table id="customers" >
      <tr>
        <th>Employee Name</th>
        <th>Mobile Number</th>
        <th>File Name</th>
        <th>Download</th>
        <th>Confirm Approval</th>
      </tr>

      <tr v-for="inf in info" :key="inf.sid">
        <td style="font-size: 15px;"> {{ inf.ename }}</td>
        <td style="font-size: 15px;">{{ inf.mobile }}</td>
        <td style="font-size: 15px;">{{ inf.name }}</td>
        
        <td class="container-login100-form-btn">
          <button>
            <a
              :href="
                'http://localhost/php_test/downloads.php?file_id=' + inf.id
              "
              class="btn"
            >
             <b>  Download </b>
            </a>
          </button>
        </td>

        <td class="container-login 00-form-btn">

          <button>
            <router-link to="/set" class="nav-link"> <d> Approved </d></router-link>
          </button>

          <button style="height:31.2px; width:80px;"
            @click="
              () => {
                deleteProfile(inf.id);
              }
            "
          >
            <b> Reject </b>
          </button> 




        </td>
      </tr>
       

      <!-- <tr>
         <div v-for="inf in info" :key="inf.sid"> 
            <td>  Name: {{inf.name }} </td>

         </div>

    </tr> -->
    </table>
  </div>
</template>

<script>
import axios from "axios";
import Nav from "./Nav";


export default {
  name: "Download",
 components: {
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
        .get("/fileview.php")
        .then((response) => (this.info = response.data));
    },

    deleteProfile(id) {
      console.log("hello");
      // return 'http://localhost/php_test/delete.php?id='+ this.inf.id ;
      axios.post("/deletefile.php?id=" + id).then(this.fetchInfo());
    },
  },
};
</script>

<!--

<script>
import axios from 'axios'

import Nav2 from './Nav2.vue'

export default{
    name: 'Profile',
    components:{
            Nav2
    },


  data () {
    return {
      info: ''
    }
  },
  mounted () {
    axios
      .get('/readall.php')
      
      .then(response => (this.info = response.data))
       
  }
}

</script>

-->

<style scoped>
#customers {
  font-family: Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  width: 70%;
    margin-left: auto;
  margin-right: auto;
  
}

#customers td,
#customers th {
  border: 1px solid #ddd;
  padding: 12px;
}

#customers tr:nth-child(even) {
  background-color: #f2f2f2;
}

#customers tr:hover {
  background-color: #ddd;
}

#customers th {
  padding-top: 12px;
  padding-bottom: 12px;
  font-size: medium;
  text-align: center;
  background-color: #175e4f;
  color: white;
}

td {
  text-align: center;
}


.btn-group button {
  background-color: hsl(156, 100%, 99%); /* Green background */
  border: 1px solid #fdfffe; /* Green border */
  color: white; /* White text */
  padding: 10px 24px; /* Some padding */
  cursor: pointer; /* Pointer/hand icon */
  float: left; /* Float the buttons side by side */
}

/* Clear floats (clearfix hack) */
.btn-group:after {
  content: "";
  clear: both;
  display: table;
}

.btn-group button:not(:last-child) {
  border-right: none; /* Prevent double borders */
}

</style>
