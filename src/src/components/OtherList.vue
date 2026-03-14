<template>
    <div class="btnArea columnCenter ">
        <div class="areaTitle">😄其他作品</div>
        <diiv class="rowCenter">
            <button class="appCard" v-for="app in apps" v-bind:key="app.title" @click="linkTap(app)">
                <img class="appImg" :src="app.img" />
                <div class="column">
                    <div class="appTitle">{{ app.title }}</div>
                    <div class="appMessage">{{ app.message }}</div>
                </div>
            </button>
        </diiv>
    </div>
</template>

<script>
export default {
    name: 'AppList',
    data() {
        return {
            apps: [
                { title: '今潮向', message: '微信公众号AI媒体。每日一推，聚合AI精选要闻与全网平台热榜', img: require('@/assets/img/other/xiaojin.jpg'), url: 'https://misuqian.gitbook.io/jin-chao-xiang' },
            ],
        }
    },
    methods: {
        linkTap(link) {
            if (!link || !link.url) return;
            let url = link.url;
            window.open(url, '_blank');
        }
    }
}
</script>

<style scoped>
.areaTitle {
    font-size: 24px;
    font-weight: bold;
    margin: 6px 0 12px 0;
    text-align: center;
    width: 200px;
    border: 2px solid #333;
}

.appCard {
    height: 88px;
    background-color: #fff;
    border: #333 2px solid;
    border-radius: 8px;
    display: flex;
    flex-direction: row;
    align-items: center;
    padding: 2px 10px;
    font-size: 18px;
    margin: 0 24px 16px 0;
    width: 350px;
}

.appCard .appTitle {
    font-weight: bold;
}

.appCard .appMessage {
    font-size: 14px;
    text-align: left;
}

.appCard .appImg {
    width: 48px;
    height: 48px;
    color: #333;
    margin: 0 8px 0 4px;
    border-radius: 8px;
}

.appCard:hover {
    background-color: #e5e5e5;
    color: #000;
}
</style>

