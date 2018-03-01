<template lang='pug'>
.vue-stop-watch
    h1 StopWatch

    p.time 00:00:00:00

    div.row
    button.a START
    button.b STOP
    button.c RESET

</template>

<script lang='ts'>
import { Vue, Component } from 'vue-property-decorator';
import VueUtil from '@/scripts/util/VueUtil';
import BuefyVue from '@/components/base/BuefyVue';

/**
 * Vue Component
 */
@Component
export default class StopWatch extends BuefyVue {
}

// var timerId;
// var count = 0;

// var msec = 0;
// var sec = 0;
// var min = 0;
// var hour = 0;

// var msecNumber;
// var secNumber;
// var minNumber;
// var hourNumber;

// function countup() {
//     msec += 1;
//     if (msec > 99) {
//         msec = 0;
//         sec += 1;
//     }

//     if (sec > 59) {
//         sec = 0;
//         min += 1;
//     }

//     if (min > 59) {
//         min = 0;
//         hour += 1;
//     }

//     msecNumber = msec;

//     if (sec < 10) {
//         secNumber = '0' + sec.toString();
//     } else {
//         secNumber = sec;
//     }


//     if (min < 10) {
//         minNumber = '0' + min.toString();
//     } else {
//         minNumber = min;
//     }

//     if (hour < 10) {
//         hourNumber = '0' + hour.toString();
//     } else {
//         hourNumber = hour;
//     }

//     $('#time').html(hourNumber + ':' + minNumber + ':' + secNumber + ':' + msecNumber);
// }

// function onKeyClick(key) {
//     if(typeof key == String.name.toLowerCase()){
//         switch (key) {
//             case 'a':{
//                 timerId = setInterval(countup, 10);
//                 break;
//              }

//                 case 'b':
//                 clearInterval(timerId);
//                 break;

//                 case 'c':
//                 msec = 0;
//                 sec  = 0;
//                 min  = 0;
//                 hour = 0;
//                 $('#time').html('00:00:00:00')
//                 break;
//         }
//     }
// }
</script>

<style lang='sass' scoped>
.vue-stop-watch
</style>
