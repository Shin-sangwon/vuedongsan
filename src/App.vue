<template>
  <div class="menu">
    <!--반복문은 태그 v-for="작명 in 몇회" :key="작명" (key 안쓰면 에러남)!-->
    <!-- '몇회' 부분에 자료(array / object)를 집어 넣어서 반복문으로 사용할 수도 있음-->
    <!-- key는 반복문 돌린 요소를 구분하기 위해 사용하는 것-->
    <!-- 작명 부분은 2개까지 할 수 있음 <a v-for="(a, i) in menus" ... i는 0부터 1씩 증가하는 정수-->
    <a v-for="nav in menus" :key="nav"> {{ nav }}</a>
  </div>

  <div>
    <h2 class="red" :style="mystyle">원룸샵</h2>
  </div>
  <div>
    <h4>XX 원룸</h4>
    <p>{{ price2 }} 만원</p>
    <!-- v-on:click == @click-->
    <!-- 함수는 ()을 제외하고 사용해야함 -->
    <button @click="increase">허위매물신고</button>
    <span>신고수 : {{ report[0] }}</span>
    <button @mouseover="increase">허위매물신고</button>
    <span>신고수 : {{ report[0] }}</span>
  </div>
  <div>
    <img src="./assets/room0.jpg" class="room-img" />
    <h4>{{ products[0] }}</h4>
    <p>{{ price2 }} 만원</p>
    <button @click="report[1]++">허위매물신고</button>
    <span>신고수 : {{ report[1] }}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img" />
    <h4>{{ products[1] }}</h4>
    <p>{{ price1 }} 만원</p>
    <button @click="report[2]++">허위매물신고</button>
    <span>신고수 : {{ report[2] }}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img" />
    <h4>{{ products[2] }}</h4>
    <p>{{ price2 }} 만원</p>
    <button @click="report[3]++">허위매물신고</button>
    <span>신고수 : {{ report[3] }}</span>
  </div>
</template>

<script>
export default {
  name: "App",
  // 데이터 보관 함 부터 만들어야 함
  // 데이터 바인딩 하는 이유
  // 1. HTML에 하드코딩해놓으면 나중에 변경이 어려움
  //★2. VUE의 실시간 자동 렌더링 기능을 사용하기 위해
  // 3. HTML 속성도 데이터바인딩 가능하다. ({{}} 대신 : 문법 사용해야 함)
  data() {
    return {
      price1: 60,
      price2: 70,
      mystyle: "color : blue",
      report: [0, 0, 0, 0],
      menus: ["Home", "Shop", "About"],
      products: ["장덕동원룸", "수완동원룸", "첨단원룸"],
    };
  },

  methods: {
    increase() {
      // this로 나의 object를 지정해야함
      this.report[0]++;
    },
  },
  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}
</style>
