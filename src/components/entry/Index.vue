<template lang='pug'>
.vue-index
    .reactive-title {{ reactiveTitle() }}
    stop-watch
</template>

<script lang='ts'>
import { Vue, Component } from 'vue-property-decorator';
import VueUtil from '@/scripts/util/VueUtil';
import RootVue from '@/components/base/RootVue';
import StopWatch from '@/components/part/StopWatch.vue';

import 'mdi/scss/materialdesignicons.scss';
import Buefy from 'buefy';
import 'buefy/lib/buefy.min.css';

Vue.use(Buefy);

/**
 * Vue Component
 */
@Component
export default class Index extends RootVue {
    public title: string = 'StopWatch';

    protected beforeCreate(): void {
        // Inner Vue 登録
        VueUtil.registerComponents([StopWatch]);
    }
}
</script>

<style lang='sass'>
@import '../../styles/color.sass'
@import '../../styles/common.sass'

.vue-index
    padding: 16px
</style>
