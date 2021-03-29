<template>
        <b-sidebar id="my-sidebar" shadow width='80%' no-header>
            <nav class="nav">
            <span class="close-nav-icon">
                <b-icon v-b-toggle.my-sidebar icon="x" font-scale="2"></b-icon>
            </span>
            <ul class="nav-list">
                <li><a href="">ホーム</a></li>
                <li><a href="">労働者情報</a></li>
                <li><a href="">プライバシーポリシー</a></li>
                <li><a href="">利用規約</a></li>
                <li><a href="">お問い合わせ</a></li>
                <li><a href=""><img src="../assets/line.png" alt="" class="line-icon"></a></li>
            </ul>
            </nav>
        </b-sidebar>
</template>

<script>
export default {
    name: 'Sidebar',
    methods: {
        
    }
}
</script>

<style scoped>
.nav {
    padding: 30px 15px;
}
.nav-list {
    margin: 0;
    padding: 0;
    width: 100%;
    list-style: none;
}
.nav-list li {
    border-bottom: 1px solid #ddd;
}
.nav-list li:last-child {
    border: none;
}
.nav-list li + li {
    margin-top: 10px;
}
.nav-list a {
    display: block;
    padding: 5px 10px;
    text-decoration: none;
    color: #333;
}
.close-nav-icon {
    position: absolute;
    top: 10px;
    right: 15px;
}
.line-icon {
    width: 30px;
}
</style>