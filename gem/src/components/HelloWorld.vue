<template>
  <div class="header">
    <div class="header1">
      <img src="../assets/logo.png" alt="logo" width="50" height="50" style="margin: 0 0 15px 0;"/>
      <span style="color: white; font-weight: 750; font-size: 40px"
        >THEGEM</span
      >
      <button class="btn" style="padding: 14px 28px">HOME</button>
      <button class="btn">PAGES</button>
      <button class="btn">BLOG</button>
      <button class="btn">FORTFOLIOS</button>
      <button class="btn">SHOP</button>
      <button class="btn">FEATURES</button>
      <button class="btn">ELEMENTS</button>
      <img src="../assets/logo.png" alt="Lights" width="25" height="15" />
      <i
        class="fa fa-search"
        style="padding: 14px 28px; font-size: 25px; color: white"
      ></i>
      <i class="material-icons" style="font-size: 30px; color: white"
        >shopping_basket</i
      >
      <img src="../assets/logo.png" alt="Lights" width="25" height="15" />
    </div>
    <div class="slideshow-container">
      <div class="mySlides fade">
        <div class="text" style="margin-bottom: 150px;">
          <i class="material-icons" style="font-size:36px">format_list_bulleted</i>
          <section>
            <span style="font-size: 40px;">SPRISING <b>TABLE</b></span>
          <p style="max-width: 1000px;
    padding: 0 0 0 300px;">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat</p>
          <br>
          <button class="btn-slide" type="text">Purchase Now</button>
          <button class="btn-slide" type="text">More Detail</button>
          </section>
        </div>
      </div>

      <div class="mySlides fade">
        <div class="text">Caption Two</div>
      </div>

      <div class="mySlides fade">
        <div class="text">Caption Three</div>
      </div>

      <a class="prev" @click="plusSlides(-1)">&#10094;</a>
      <a class="next" @click="plusSlides(1)">&#10095;</a>
    </div>
    <div style="text-align: center">
      <span class="dot" @click="currentSlide(1)"></span>
      <span class="dot" @click="currentSlide(2)"></span>
      <span class="dot" @click="currentSlide(3)"></span>
    </div>
  </div>
</template>

<script>
export default {
  // name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
      slideIndex: 1,
    };
  },
  methods: {
    plusSlides(n) {
      this.showSlide((this.slideIndex += n));
      console.log((this.slideIndex += n));
    },
    currentSlide(n) {
      this.showSlide((this.slideIndex = n));
    },
    showSlide(n) {
      var i;
      var slides = document.getElementsByClassName("mySlides");

      var dots = document.getElementsByClassName("dot");
      if (n > slides.length) {
        this.slideIndex = 1;
      }
      if (n < 1) {
        this.slideIndex = slides.length;
      }
      for (i = 0; i < slides.length; i++) {
        slides[i].style.display = "none";
      }
      for (i = 0; i < dots.length; i++) {
        dots[i].className = dots[i].className.replace(" active", "");
      }
      slides[this.slideIndex - 1].style.display = "block";
      dots[this.slideIndex - 1].className += " active";
    },
  },
  mounted() {
    this.showSlide(this.slideIndex);
  },
};
</script>

<style scoped>
@import url(https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css);
@import url(https://fonts.googleapis.com/icon?family=Material+Icons);
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.header {
  background-color: #2c2e3d;
  opacity: 0.6;
}
.header1{
  text-align: center;
}
.btn {
  border: none;
  background-color: inherit;
  padding: 14px 38px;
  font-size: 16px;
  cursor: pointer;
  display: inline-block;
  color: #99a9b5;
}
.btn:hover {
  color: #00bcd4;
}
.btn-slide{
    border-radius: 50px;
    width: 220px;
    height: 50px;
    background-color: #2b2d3d;
    border-style: ridge;
    border-color: white;
    color: white;
    margin: 20px;
}
.btn-slide:hover{
  color: #00bcd4;
  border-color: #00bcd4;
}
.mySlides {
  display: none;
}
img {
  vertical-align: middle;
}
.slideshow-container {
  width: 100%;
  position: relative;
  margin: auto;
  height: 850px;
}
.prev,
.next {
  cursor: pointer;
  position: absolute;
  top: 50%;
  width: auto;
  padding: 16px;
  margin-top: -22px;
  color: white;
  font-weight: bold;
  font-size: 18px;
  transition: 0.1s ease;
  border-radius: 0 3px 3px 0;
  user-select: none;
}
.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}
.prev:hover,
.next:hover {
  background-color: #00bcd4;
}
.text {
  color: #f2f2f2;
  font-size: 15px;
  padding: 8px 12px;
  position: absolute;
  bottom: 8px;
  width: 100%;
  text-align: center;
}
.dot {
  cursor: pointer;
  height: 15px;
  width: 15px;
  margin: 0 2px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}
.active,
.dot:hover {
  background-color: #717171;
}
.fade {
  -webkit-animation-name: fade;
  -webkit-animation-duration: 1.5s;
  animation-name: fade;
  animation-duration: 1.5s;
}

@-webkit-keyframes fade {
  from {
    opacity: 0.4;
  }
  to {
    opacity: 1;
  }
}

@keyframes fade {
  from {
    opacity: 0.4;
  }
  to {
    opacity: 1;
  }
}
@media only screen and (max-width: 300px) {
  .prev,
  .next,
  .text {
    font-size: 11px;
  }
}
</style>
