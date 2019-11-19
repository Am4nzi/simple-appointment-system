<template>
  <div id="main-app" class="container">
    <div class="row"></div>
    <appointment-list :appointments="appointments" />

  </div>
</template>

<script>
import AppointmentList from "./components/AppointmentList";
import axios from "axios";

export default {
  name: "MainApp",
  data: function() {
    return {
      title: "Appointment List",
      appointments: []
    };
  },
  components: {
    AppointmentList
  
  },
  mounted() {
    axios
      .get("./data/appointments.json")
      .then(response => (this.appointments = response.data));
  }
};
</script>
