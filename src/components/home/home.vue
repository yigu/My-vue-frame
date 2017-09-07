<template>
    <section class="home_section">
        <carousel></carousel>
        <ul class="nav-tabs" v-on:click='clickTabs'>
            <li class="active">Data1</li>
            <li>Data2</li>
        </ul>

        <list v-show="show1" :items="data1"/>
        <list v-show="!show1" :items="data2"/>
    </section>
</template>

<script>
var img = require('@/assets/banner.jpg');
import config from '../../const.js'

export default{
    name: 'home_section',
    data () {
        return {
            show1: true,
            show2: false,
            data1: [],
            data2: [{img: img, title: 'aaaaaaaaaaaaaaa'}]
        }
    },
    methods: {
        clickTabs (event) {
            document.getElementsByClassName('active')[0].className = '';
            event.target.classList = ['active'];
            if (event.target.innerText === 'Data1') {
                this.show1 = true;
                this.show2 = false;
            } else {
                this.show1 = false;
            }
        }
    },
    components: {
        'list': require('../../basic/list.vue'),
        'carousel': require('../../basic/carousel.vue')
    },
    created () {
        $.ajax({
            type: 'get',
            url: config.url + '/v1.0/index?pagesize=10&offset=0',
            dataType: 'json',
            success: data => { // => 可保证this指向vue实例
                this.data1 = data.data.lessonList;
            },
            error: data => {
                this.data1 = [{img: img, title: '服务器获取失败'}];
            }
        })
    }
}
</script>

<style scoped>
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