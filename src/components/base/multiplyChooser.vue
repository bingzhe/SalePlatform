<template>
    <div class="chooser-component">
        <ul class="chooser-list">
            <li v-for="(item, index) in selections" @click="toggleSelecion(index)" :title="item.label" :class="{active: checkActive(index)}">{{ item.label }}</li>
        </ul>
    </div>
</template>

<script>
import _ from 'lodash'
export default {
    props: {
        selections: {
            type: Array,
            default: [{
                label: 'test',
                value: 0
            }]
        }
    },
    data() {
        return {
            nowIndex: [0]
        }
    },
    methods: {
        toggleSelecion(index) {
            let shiftIndex
            let nowObjArray = []
            if (this.nowIndex.indexOf(index) === -1) {
                this.nowIndex.push(index)
            }
            else {
                shiftIndex = this.nowIndex.indexOf(index)
                this.nowIndex.splice(shiftIndex, 1)
            }
            this.nowIndex.forEach((element, index, array) => {
                nowObjArray.push(this.selections[element])
            })
            //  nowObjArray = _.map(this.nowIndex, (idx) => {
            //     return this.selections[idx]
            // })
            this.$emit('on-change', nowObjArray)
        },
        checkActive(index) {
            return this.nowIndex.indexOf(index) !== -1
        }
    }
}
</script>

<style scoped>
.chooser-component {
    position: relative;
    display: inline-block;
}

.chooser-list li {
    display: inline-block;
    border: 1px solid #e3e3e3;
    height: 25px;
    line-height: 25px;
    padding: 0 8px;
    margin-right: 5px;
    border-radius: 3px;
    text-align: center;
    cursor: pointer;
}

.chooser-list li.active {
    border-color: #4fc08d;
    background: #4fc08d;
    color: #fff;
}
</style>


