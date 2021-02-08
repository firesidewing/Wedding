<template>
    <div>
        <p>
          <a class="map-link" href="https://goo.gl/maps/YQdVBMBpsmZ9Fpog6" target="_blank">
            <i class="gg-pin"></i>
            <span>Directions</span>
          </a>
        </p> 
    </div>
</template>

<script>
export default {

}
</script>

<style>
.map-link {
  display:flex;
  justify-content: center;
  align-items: center;
  text-decoration: none;
  color: #b6b6b6;
  font-size:1.5rem;
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