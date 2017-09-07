<template>
    <div id="sliderWrap">
        <ul class="slider-content">
            <li>
                <a href="javascript:void (0)">
                    <img src="http://ww1.sinaimg.cn/large/a660cab2gy1fdeop4kdmpj20ms0e83z6" alt="" />
                </a>
            </li>
            <li>
                <a href="javascript:void (0)">
                    <img src="http://ww1.sinaimg.cn/large/a660cab2gy1fdeophraf0j20ms0e8ab1" alt="" />
                </a>
            </li>
            <li>
                <a href="javascript:void (0)">BC
                    <img src="http://ww1.sinaimg.cn/large/a660cab2gy1fdeopsmhmnj20ms0e8weq" alt="" />
                </a>
            </li>
        </ul>
        <ul class="slider-flag">
            <li class="active"></li>
            <li></li>
            <li></li>
        </ul>
    </div>
</template>
<script>
require('../lib/slider.js');
export default {
    mounted () {
        new Slider('#sliderWrap', {interval: 5000});
    }
};

</script>
<style scoped>
* {
    margin: 0;
    padding: 0;
}

#sliderWrap {
    margin: 0 auto;
    width: 100%;
    position: relative;
    font-size: 0;
    overflow: hidden;
}

#sliderWrap .slider-content {
    height: 100%;
    transition: 0.5s ease-out;
    margin: 0;
    padding: 0;
}

#sliderWrap .slider-content li {
    height: 100%;
    list-style: none;
    display: inline-block;
}

#sliderWrap .slider-content li img {
    width: 100%;
    height: 100%;
    vertical-align: top;
}

#sliderWrap .slider-flag {
    position: absolute;
    margin: 0;
    padding: 0;
    bottom: 8%;
    left: 50%;
    transform: translateX(-50%);
    -webkit-transform: translateX(-50%);
    height: 15px;
}

#sliderWrap .slider-flag li {
    width: 10px;
    height: 10px;
    border-radius: 100%;
    border: 1px solid;
    display: inline-block;
    margin: 0 4px;
}

#sliderWrap .slider-flag li.active {
    background-color: #79ff79;
    border: 1px solid #79ff79;
}  
</style>