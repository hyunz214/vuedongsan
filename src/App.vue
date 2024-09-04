<template>
    <div class="menu">
        <a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
    </div>
    <div>
        <h4>{{ products[0] }}</h4>
        <p>{{ price1 }} 만원</p>
        <button @click="increase">허위매물 신고</button>
        <span>신고수 : {{ 신고수 }}</span>
    </div>
    <div>
        <h4>{{ products[1] }}</h4>
        <p>{{ price2 }} 만원</p>
    </div>
    <div>
        <h4>{{ products[2] }}</h4>
        <p>{{ price3 }} 만원</p>
    </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";

export default {
    name: "App",
    data() {
        return {
            신고수: 0,
            price1: 60,
            price2: 70,
            price3: 40,
            menus: ["Home", "Products", "About"],
            products: ["역삼동 원룸", "천호동 원룸", "마포구 원룸"],
        };
    },
    methods: {
        increase() {
            this.신고수 += 1;
        },
    },
    components: {
        // HelloWorld,
    },
};
</script>

<style>
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
</style>
