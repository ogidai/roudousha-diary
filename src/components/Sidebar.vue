<template>
        <b-sidebar id="my-sidebar" shadow width='80%' no-header>
            <nav class="nav">
            <span class="close-nav-icon">
                <b-icon v-b-toggle.my-sidebar icon="x" font-scale="2"></b-icon>
            </span>
            <ul class="nav-list">
                <li><router-link to="/">ホーム</router-link></li>
                <li><router-link to="/post">日記を書く</router-link></li>
                <li><router-link to="/user">労働者情報</router-link></li>
                <li><router-link to="/privacypolicy">プライバシーポリシー</router-link></li>
                <li><router-link to="/terms">利用規約</router-link></li>
                <li><router-link to="/contact">お問い合わせ</router-link></li>
                <li><a href=""><img src="../assets/line.png" alt="" class="line-icon"></a></li>
            </ul>
            </nav>
        </b-sidebar>
</template>

<script>
export default {
    name: 'Sidebar',
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