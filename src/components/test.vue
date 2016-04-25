<template>
    <input type="text" @click="showCalendar" v-model="value" placeholder="">
    <calendar :show.sync="show" :value.sync="value" :x="x" :y="y" :begin="begin" :end="end" :range="range"></calendar>
</template>

<script>
    module.exports = {
        data: function() {
            return {
                show:false,
                type:"date",
                value:"2015-12-11",
                begin:"2015-12-20",
                end:"2015-12-25",
                x:0,
                y:0,
                range:true,
            }
        },
        methods:{
            showCalendar:function(e){
                e.stopPropagation();
                var that=this;
                that.show=true;
                that.x=e.target.offsetLeft;
                that.y=e.target.offsetTop+e.target.offsetHeight+8;
                var bindHide=function(e){
                    e.stopPropagation();
                    that.show=false;
                    document.removeEventListener('click',bindHide,false);
                };
                setTimeout(function(){
                    document.addEventListener('click',bindHide,false);
                },500);
            }
        }
    }
</script>
