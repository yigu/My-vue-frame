<template>
    <section class="item-list" v-show="showList">
        <div class="list-div" v-for="item in items">
            <img v-bind:src="item.img">
            <p>{{item.name}}</p>
        </div>
    </section>
</template>
<script>
export default {
    props: ['showList', 'items']
};
</script>

<style scoped>
img {
    width: 100%;
    height: 200px;
}
p {
    margin: 0px 0px 10px 0px;
    text-align: left;
}
.list-div {
    margin-bottom: 10px;
    border-bottom: 1px solid #ddd;
}
</style>