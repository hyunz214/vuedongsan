<template>
    <div class="black-bg" v-if="isOpenModal == true">
        <div class="white-bg">
            <h4>상세페이지임</h4>
            <p>상세페이지 내용임</p>
            <button @click="isOpenModal = false">닫기</button>
        </div>
    </div>

    <div class="menu">
        <a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
    </div>
    <div>
        <img src="./assets/images/room0.jpg" class="room-img" />
        <h4 @click="isOpenModal = true">{{ products[0] }}</h4>
        <p>{{ price1 }} 만원</p>
        <button @click="increase(0)">허위매물 신고</button>
        <span>신고수 : {{ 신고수[0] }}</span>
    </div>
    <div>
        <img src="./assets/images/room1.jpg" class="room-img" />
        <h4>{{ products[1] }}</h4>
        <p>{{ price2 }} 만원</p>
        <button @click="increase(1)">허위매물 신고</button>
        <span>신고수 : {{ 신고수[1] }}</span>
    </div>
    <div>
        <img src="./assets/images/room2.jpg" class="room-img" />
        <h4>{{ products[2] }}</h4>
        <p>{{ price3 }} 만원</p>
        <button @click="increase(2)">허위매물 신고</button>
        <span>신고수 : {{ 신고수[2] }}</span>
    </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";

export default {
    name: "App",
    data() {
        return {
            isOpenModal: false,
            신고수: [0, 0, 0],
            price1: 60,
            price2: 70,
            price3: 40,
            menus: ["Home", "Products", "About"],
            products: ["역삼동 원룸", "천호동 원룸", "마포구 원룸"],
        };
    },
    methods: {
        increase(i) {
            this.신고수[i] += 1;
        },
    },
    components: {
        // HelloWorld,
    },
};
</script>

<style>
body {
    margin: 0;
}
div {
    box-sizing: border-box;
}
.black-bg {
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    position: fixed;
    padding: 20px;
}
.white-bg {
    width: 100%;
    background: white;
    border-radius: 8px;
    padding: 20px;
}
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}
.menu {
    background: darkblue;
    padding: 16px;
    border-radius: 4px;
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
