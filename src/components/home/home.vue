<template>
    <section class="home_section">
        <img class="banner" src="../../assets/banner.jpg">
        <ul class="nav-tabs" v-on:click='clickTabs'>
            <li class="active">Data1</li>
            <li>Data2</li>
        </ul>

        <list :show-list="show1" :items="data1"/>
        <list :show-list="show2" :items="data2"/>
    </section>
</template>

<script>
var img = require('@/assets/banner.jpg');
import $ from 'jquery'

export default{
    name: 'home_section',
    data () {
        return {
            show1: true,
            show2: false,
            data1: [{img: img, name: 'jjjjjjjjjjjjjjj'}],
            data2: [{img: img, name: 'aaaaaaaaaaaaaaa'}]
        }
    },
    methods: {
        clickTabs (event) {
            document.getElementsByClassName('active')[0].className = '';
            event.target.classList = ['active'];
        }
    },
    components: {
        'list': require('../../basic/list.vue')
    },
    created () {
        var _self = this;
        $.ajax({
            type: 'get',
            url: '/',
            dataType: 'json',
            success: function () {
            },
            error: function () {
                _self.data1 = [{img: img, name: 'jjjjjjjjjjjjjjj'},
                {img: img, name: 'jjjjjjjjjjjjjjj'}, {img: img, name: 'jjjjjjjjjjjjjjj'}];
            }
        })
    }
}
</script>

<style scoped>
.banner {
  width: 100%;
}
.nav-tabs {
  width: 100%;
  padding-left: 0px;
}
.nav-tabs>li {
    margin-bottom: -1px;
    position: relative;
    display: inline-block;
    cursor: pointer;
    line-height: 1.42857143;
    border-bottom: 1px solid #ddd;
    border-radius: 4px 4px 0 0;
    padding: 10px 0px;
    text-decoration: none;
    width: 48%;
    margin-left: -8px;
}
.nav-tabs>li.active, nav-tabs>li.active:hover {
    color: green;
    background-color: #fff;
    border: 1px solid #ddd;
    border-bottom-color: transparent;
}
</style>