<template>
  <div id="nav-bar">
    <router-link to="/" id="homepage-link">
      <div id="logo-wrap">
        <img src="../assets/logo.png" alt="logo" />
      </div>
    </router-link>
    <router-link to="/cart" id="cart-link">
      <button class="shopping-cart-btn">GO TO CART</button>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'NavBar',
};
</script>

<style scoped>
#nav-bar {
  border-bottom: 1px solid #ddd;
  height: 75px;
  width: 100%;
  background: whitesmoke;
}

#products-link,
#homepage-link {
  text-align: center;
  display: block;
  color: black;
  font-size: 22px;
  left: 32px;
  position: absolute;
  top: 0;
  text-decoration: none;
}

.shopping-cart-btn {
  background: transparent;
  color: #006a89;
  border: 1px solid #006a89;
  border-radius: 0;
}

shopping-cart-btn:hover {
  background: #006a89;
  color: white;
  border: 1px solid #006a89;
}

#products-link h1 {
  margin: 0;
}

#cart-link {
  position: absolute;
  right: 16px;
  top: 16px;
}

#logo-wrap {
  width: 100px;
  height: 80px;
}

#logo-wrap img {
  width: 100%;
  height: 100%;
}
</style>
