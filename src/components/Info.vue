<template>
  <div class="row">
  <div class="column">
    <img lazy="true" src="@/assets/3.jpg">    
    <img lazy="true" src="@/assets/1.jpg">       
  </div>
  <div class="column">  
    <img lazy="true" src="@/assets/2.jpg"> 
    <img lazy="true" src="@/assets/apron-min.jpg">    
  </div>
  <div class="column">
    <img lazy="true" src="@/assets/4.jpg">
    <img lazy="true" src="@/assets/5.jpg">
    
  </div>
   <div class="column">
    <img lazy="true" src="@/assets/6.jpg">
    <img lazy="true" src="@/assets/7.jpg">
    <img lazy="true" src="@/assets/8.jpg">
  </div>
</div>
</template>

<script>
export default {

}
</script>

<style>
.row {
  display: flex;
  flex-wrap: wrap;
  padding: 0 0.5rem;
}

/* Create four equal columns that sits next to each other */
.column {
  flex: 20%;
  max-width: 25%;
  padding: 0 0.5rem;
}

.column img {
  margin-top: 0.5rem;
  vertical-align: middle;
  width: 100%;
}

/* Responsive layout - makes a two column-layout instead of four columns */
@media screen and (max-width: 700px) {
  .column {
    flex: 50%;
    max-width: 50%;
  }
}

/* Responsive layout - makes the two columns stack on top of each other instead of next to each other */
@media screen and (max-width: 600px) {
  .column {
    flex: 100%;
    max-width: 100%;
  }
}
</style>