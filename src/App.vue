<template>
    <div class="black-bg" v-if="모달창열렸니 == true">
        <div class="white-bg">
            <h4>상세페이지임</h4>
            <p>상세페이지 내용임</p>
            <button @click="모달창열렸니 = false">닫기</button>
        </div>
    </div>
    <nav id="gnb">
        <ul>
            <li v-for="a in 메뉴들" :key="a">
                <a href="#">{{ a }}</a>
            </li>
        </ul>
    </nav>
    <div v-for="(a, i) in 원룸들" :key="i">
        <img :src="원룸들[i].image" :alt="원룸들[i].title" class="room-img" />
        <h4>{{ 원룸들[i].title }}</h4>
        <p>{{ 원룸들[i].price }}원</p>
    </div>
</template>

<script>
import data from './assets/oneroom';

export default {
    name: 'App',
    data() {
        return {
            원룸들: data,
            모달창열렸니: false,
            신고수: [0, 0, 0],
            메뉴들: ['Home', 'Shop', 'About'],
            products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
        };
    },
    methods: {
        increase() {
            this.신고수 += 1;
        },
    },
    components: {},
};
</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
li {
    list-style: none;
}
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    font-size: 16px;
}
#gnb {
    background: darkslateblue;
    padding: 15px;
}
#gnb li {
    display: inline-block;
}
#gnb li a {
    display: block;
    color: #fff;
    text-decoration: none;
    padding: 10px;
}
.room-img {
    width: 100%;
    height: auto;
    margin-top: 40px;
}
.black-bg {
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.6);
    position: fixed;
    padding: 20px;
}
.white-bg {
    width: 100%;
    background-color: #fff;
    border-radius: 8px;
    padding: 20px;
}
</style>
