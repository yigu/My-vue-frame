<template>
    <section class="item-list">
        <div class="list-div" v-for="item in items">
            <router-link to="/hello">
                <img class="item-img" v-bind:src="item.img">
                <p>{{item.title}} {{item.description}}</p>
            </router-link>
        </div>
    </section>
</template>
<script>
export default {
    props: ['items']
};
</script>

<style scoped>
.item-img {
    width: 100%;
    height: 500px;
}
p {
    margin: 15px 0px 30px 0px;
    text-align: left;
}
a {
    text-decoration: none;
    color: #2c3e50;
}
.list-div {
    margin-bottom: 30px;
    border-bottom: 1px solid #ddd;
}
</style>