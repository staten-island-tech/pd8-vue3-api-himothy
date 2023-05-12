<template>
    <div class="box">
      <div class="box-header">
        <h2>FILM: {{ id }}</h2>
      </div>
      <div class="box-body">
        <p>Borough: {{ borough }}</p>
        <p>Genre: {{ event }}</p>
        <p>Event Type: {{ eventtype }}</p>
      </div>
    </div>
  </template>
 
  <script>
  export default {
    props: {
      event: Object,
      id: Number,
      borough: String,
      eventtype: String,
    },
  };
  </script>
 
  <style scoped>
  .box {
    background-color: #f0f8ff;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
    border-radius: 10px;
    padding: 20px;
    margin: 0 auto;
    max-width: 500px;
    width: 100%;
  }
 
  .box-header {
    margin-bottom: 20px;
  }
 
  h2 {
    font-size: 24px;
    margin: 0;
  }
 
  p {
    margin: 0;
    font-size: 18px;
    line-height: 1.5;
  }
  </style>
 
