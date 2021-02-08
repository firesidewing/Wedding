<template>
    <div>
        <div class="map-link">
            <p class="p1">Location</p>
            <iframe v-if="IsMobile" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2526.4474785454763!2d-119.2496007842591!3d50.71163697951221!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x537ef45f9d66eb2f%3A0xaf13fca1262f6888!2s3270%2016%20Ave%20NE%2C%20Salmon%20Arm%2C%20BC%20V1E%202Y7!5e0!3m2!1sen!2sca!4v1612750144598!5m2!1sen!2sca" width="300" height="300" frameborder="0" style="border:0;" allowfullscreen="" aria-hidden="false" tabindex="0"></iframe>
            <iframe v-else src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2526.4474785454763!2d-119.2496007842591!3d50.71163697951221!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x537ef45f9d66eb2f%3A0xaf13fca1262f6888!2s3270%2016%20Ave%20NE%2C%20Salmon%20Arm%2C%20BC%20V1E%202Y7!5e0!3m2!1sen!2sca!4v1612750144598!5m2!1sen!2sca" width="600" height="450" frameborder="0" style="border:0;" allowfullscreen="" aria-hidden="false" tabindex="0"></iframe>
        </div>    
        <div class="info">
            <p>The ceremony and reception will be held at our home in our backyard. Parking TBD.</p>
        </div>   
    </div>
</template>

<script>
export default {
    name: 'info',
    computed: {
        IsMobile: function() {
            return window.innerWidth < 600;
        }
    }
}
</script>

<style>
.p1{
  font-family: 'Poiret One', cursive;
}
.info{
    text-align: center;
}
.map-link {
  display:grid;
  justify-content: center;
  align-items: center;
  font-size:1.5rem;
  text-align: center;
}

.gg-pin {
    box-sizing: border-box;
    position: relative;
    display: block;
    transform: rotate(45deg) scale(var(--ggs,1));
    width: 18px;
    height: 18px;
    border-radius: 100% 100% 0 100%;
    border: 2px solid;
    margin-top: -4px
}
.gg-pin::before {
    content: "";
    display: block;
    box-sizing: border-box;
    position: absolute;
    width: 8px;
    height: 8px;
    border: 2px solid;
    top: 3px;
    left: 3px;
    border-radius: 40px
}
</style>