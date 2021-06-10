<template>
  <div id="homepage-wrap">
    <img src="../assets/homepage.jpg" alt="homepage" />
    <div class="btn-wrap">
      <button class="about-us-btn">About Us</button>
      <router-link to="/products" id="products-link">
        <button class="shop-now-btn">Shop Now</button>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
};
</script>

<style>
#homepage-wrap {
  position: relative;
  height: 800px;
}

#homepage-wrap img {
  max-width: 100%;
  max-height: 100%;
  width: 100%;
}

.btn-wrap {
  display: flex;
  width: auto;
  flex-direction: row;
  position: absolute;
  top: 50%;
  right: 50%;
  width: 350px;
  justify-content: space-between;
}

.shop-now-btn,
.about-us-btn {
  text-transform: uppercase;
  border: 1px solid white;
  border-radius: 0;
  background: transparent;
  padding: 20px 30px;
}
</style>
