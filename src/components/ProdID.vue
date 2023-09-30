<script setup>
import { ref } from "vue";
import { useRoute } from "vue-router";

const route = useRoute();
const id = parseInt(route.params.id);

const CoffeeList = ref([
  { id: 1, name: 'ไอซ์ คาเฟ่ อเมริกาโน่', img: "https://www.starbucks.co.th/stb-media/2020/08/41.Iced-Caffe-Mocha1080.png"},
  { id: 2, name: 'ไอซ์ คาปูชิโน่', img: "https://www.starbucks.co.th/stb-media/2020/08/45.Iced-Cappuccino1080.png" },
  { id: 3, name: 'ไอซ์ คาเฟ่ มอคค่า', img: "https://www.starbucks.co.th/stb-media/2020/08/41.Iced-Caffe-Mocha1080.png"},
  { id: 4, name: 'ไอซ์ เพียว มัทฉะ ลาเต้', img: "https://www.starbucks.co.th/stb-media/2020/08/81.Iced-Green-Tea-Latte1080.png"},
  { id: 5, name: 'ยูสุ แบล็ค ที', img: "https://www.starbucks.co.th/stb-media/2020/08/Yuzu-Black-Tea-1080x1080-1.png" },
  { id: 6, name: 'ไอซ์ โกลเด้น มังกี้ ที ลาเต้', img: "https://www.starbucks.co.th/stb-media/2022/01/Winter2022_Web_Iced-golden-monkey-latte_GreenBG.jpg" }
]);

</script>
<template>
 <!-- Coffee Products -->
 <div class="bg-body-tertiary me-md-3 pt-3 px-3 pt-md-5 px-md-5 text-center overflow-hidden">
    <div class="my-3 p-3">
    <RouterLink to="/" class="btn-back">กลับ</RouterLink>
    <h2 class="display-5">{{ CoffeeList[id - 1].name }}</h2>
      <p class="lead">"สัมผัสความอร่อยในทุกสไตล์ของเรา" {{ id }}</p>
    </div>
    <div class="bg-dark shadow-sm mx-auto" style="width: 45%; height: 320px; margin-top: -20px; border-radius: 21px 21px 0 0;">
      <img :src="CoffeeList[id - 1].img" width="450" height="300" style="margin-top: 10px;" />
    </div> <br> <br>
    <div>
      {{ CoffeeList[id - 1].name }} <br>
      {{ CoffeeList[id - 1].text }}
    </div>
 <br> <br> <br> </div> 
  </template>
  


<style>
.btn-back {
 margin-right: 90%;
 display: inline-block;
 padding: 0.5rem 1.8rem;
 font-size: 16px;
 font-weight: 700;
 color: rgb(98, 186, 168);
 border: 3px solid rgb(4, 65, 46);
 cursor: pointer;
 position: relative;
 background-color: transparent;
 text-decoration: none;
 overflow: hidden;
 z-index: 1;
 font-family: inherit;
 border-radius: 20px;
}

.btn-back::before {
 content: "";
 position: absolute;
 left: 0;
 top: 0;
 width: 100%;
 height: 100%;
 background-color: rgb(21, 80, 54);
 transform: translateX(-100%);
 transition: all .5s;
 z-index: -1;
}

.btn-back:hover::before {
 transform: translateX(0);
}
.container {
  max-width: 960px;
}

.icon-link > .bi {
  width: .75em;
  height: .75em;
}


.site-header {
  background-color: rgba(0, 0, 0, .85);
  -webkit-backdrop-filter: saturate(180%) blur(20px);
  backdrop-filter: saturate(180%) blur(20px);
}
.site-header a {
  color: #643400;
  transition: color .15s ease-in-out;
}
.site-header a:hover {
  color: #643400;
  text-decoration: none;
}


.product-device {
  position: absolute;
  right: 0;
  bottom: -5%;
  width: 300px;
  height: 740px;
  background-color: #063d2e;
  border-radius: 21px;

}

.product-device-2 {
  left: 0;
  background-color: #063d2e;
}


.flex-equal > * {
  flex: 1;
}
@media (min-width: 768px) {
  .flex-md-equal > * {
    flex: 1;
  }
}

</style>