<template>
  <div class="menu">
    <a>Home</a>
    <a>Products</a>
    <a>About</a>
  </div>

  <img alt="Vue logo" src="./assets/logo.png" />
  <div>
    <h2 class="red" :style="mystyle">원룸샵</h2>
    <h4>XX 원룸</h4>
    <p>{{ price1 }} 만원</p>
  </div>
  <div>
    <h4>XX 원룸</h4>
    <p>{{ price2 }} 만원</p>
  </div>
  <div>
    <h4>{{ products[0] }}</h4>
    <p>{{ price2 }} 만원</p>
  </div>
  <div>
    <h4>{{ products[1] }}</h4>
    <p>{{ price1 }} 만원</p>
  </div>
  <div>
    <h4>{{ products[2] }}</h4>
    <p>{{ price2 }} 만원</p>
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
      products: ["장덕동원룸", "수완동원룸", "첨단원룸"],
    };
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
</style>
