<template>
    <div id="disp">
        <p id="ac">
            AC
        </p>
        <p id="acumulator">
            {{value}}  
        </p>
        <p id="result">
            {{result}}
        </p>
    </div>
</template>


<script setup>
defineProps({
    value:String,
    result:String,

})


</script>


<style>
#ac{
    float: left;
    font-size: smaller;
    color: rgb(141, 135, 127);
    transition: 0.2s;
}

#disp:hover #ac{
    color: rgb(230, 226, 221);
    font-size: small;
   
}


#disp{
    padding: 1px;
    min-height: 50px;
    cursor: pointer;
    transition: 0.2s;
}
p{
    margin: 1px;
    text-align: end;
}

#acumulator{
    font-size: 15px;
}
#result{
    color: rgb(46, 46, 46);
}


</style>