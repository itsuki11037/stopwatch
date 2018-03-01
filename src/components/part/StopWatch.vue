<template lang='pug'>
.vue-stop-watch
    h1 StopWatch

    p.time.columns.is-centered
        span.column.is-2 {{ String(hour).padStart(2, '0') }}
        span.column.is-narrow :
        span.column.is-2 {{ String(min).padStart(2, '0') }}
        span.column.is-narrow :
        span.column.is-2 {{ String(sec).padStart(2, '0') }}
        span.column.is-narrow :
        span.column.is-2 {{ String(msec).padStart(2, '0') }}

    .columns.is-centered
        .column.is-narrow: button.button.is-primary(@click='timerStart') START
        .column.is-narrow: button.button.is-danger(@click='timerStop') STOP
        .column.is-narrow: button.button.is-warning(@click='timerReset') RESET
</template>

<script lang='ts'>
import { Vue, Component } from 'vue-property-decorator';
import VueUtil from '@/scripts/util/VueUtil';
import BuefyVue from '@/components/base/BuefyVue';
import { setInterval, clearInterval } from 'timers';

/**
 * Vue Component
 */
@Component
export default class StopWatch extends BuefyVue {
    private timerId: NodeJS.Timer | null = null;
    private count: number = 0;

    private msec: number = 0;
    private sec: number = 0;
    private min: number = 0;
    private hour: number = 0;


    private timerStart(): void {
        this.timerId = setInterval(this.countup, 10);
    }

    private timerStop(): void {
        if (this.timerId == null) {
            return;
        }
        clearInterval(this.timerId);
    }

    private timerReset(): void {
             this.timerId = null
             this.msec = 0;
             this.sec  = 0;
             this.min  = 0;
             this. hour = 0;

    }

    private countup():void {
        this.msec++;

        if (this.msec > 99) {
            this.msec = 0;
            this.sec++;
        }

        if (this.sec > 59) {
            this.sec = 0;
            this.min++;
        }

        if (this.min > 59) {
            this.min = 0;
            this.hour++;
        }
    }
}

</script>

<style lang='sass' scoped>
@import '~bulma'

.vue-stop-watch
    max-width: 700px
    width: 80%
    margin: 0 auto

    .time
        margin: 16px auto

        & > span
            text-align: center
            font-size: $size-1

    h1
        font-size: 40px
</style>
