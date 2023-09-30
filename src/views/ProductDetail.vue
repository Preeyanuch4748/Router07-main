<script setup>
import{ ref } from "vue";

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
    <div class="bg-body-tertiary me-md-3 pt-3 px-3 pt-md-5 px-md-5 text-center overflow-hidden"
      v-for="(coffee, index) in CoffeeList"
      :key="index"
    >
      <div class="my-3 p-3">
        <h2 class="display-5">{{ coffee.name }}</h2>
        <p class="lead">"สัมผัสความอร่อยในทุกสไตล์ของเรา" {{ index+1 }}</p>
      </div>
      <div
        class="bg-dark shadow-sm mx-auto"
        style="width: 45%; height: 320px; margin-top: -20px; border-radius: 21px 21px 0 0;"
      >
        <img :src="coffee.img" width="450" height="300" style="margin-top: 10px;" />
      </div>
      <div class="d-flex gap-2 justify-content-center py-5">
        <RouterLink :to="{name:'coffee', params: {id: coffee.id }}" class="button" type="button">
          รายละเอียด {{ index+1 }} &nbsp;
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="20"
            height="20"
            fill="currentColor"
            class="bi bi-arrow-right"
            viewBox="0 1 16 16"
          >
            <path
              fill-rule="evenodd"
              d="M1 8a.5.5 0 0 1 .5-.5h11.793l-3.147-3.146a.5.5 0 0 1 .708-.708l4 4a.5.5 0 0 1 0 .708l-4 4a.5.5 0 0 1-.708-.708L13.293 8.5H1.5A.5.5 0 0 1 1 8z"
            />
          </svg>
        </RouterLink>
      </div>
    </div>
  </template>
  


<style>
.button {
 --color: #033b26;
 padding: 0.8em 1.7em;
 background-color: transparent;
 border-radius: .3em;
 position: relative;
 overflow: hidden;
 cursor: pointer;
 transition: .5s;
 font-weight: 400;
 font-size: 17px;
 border: 1px solid;
 font-family: inherit;
 text-transform: uppercase;
 color: var(--color);
 z-index: 1;
}

.button::before, .button::after {
 content: '';
 display: block;
 width: 50px;
 height: 50px;
 transform: translate(-50%, -50%);
 position: absolute;
 border-radius: 50%;
 z-index: -1;
 background-color: var(--color);
 transition: 1s ease;
}

.button::before {
 top: -1em;
 left: -1em;
}

.button::after {
 left: calc(100% + 1em);
 top: calc(100% + 1em);
}

.button:hover::before, .button:hover::after {
 height: 410px;
 width: 410px;
}

.button:hover {
 color: rgb(203, 251, 237);
}

.button:active {
 filter: brightness(.8);
}

.container {
  max-width: 960px;
}

.icon-link > .bi {
  width: .75em;
  height: .75em;
}


.site-header {
  background-color: rgba(0, 45, 11, 0.914);
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
  background-color: rgb(12, 62, 5);
  border-radius: 21px;

}

.product-device-2 {
  left: 0;
  background-color: rgb(12, 62, 5);
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