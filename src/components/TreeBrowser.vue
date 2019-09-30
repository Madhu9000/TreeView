<template>
<div >
    <div @click="nodeClicked" :style="{'margin-left': `${depth * 20}px`}" class="node">
        <span v-if="hasChildren" class="type">
            <i v-if="!expanded" class="fa fa-caret-right"></i>
        </span>
        <span class="type" v-else>
            <i class="fa fa-circle"></i>
        </span>
        <span :style="getStyle(node)">{{node.name}}</span>
    </div>
    <ul v-if="expanded">
        <TreeBrowser v-for="child in node.children" :key="child.name" :node="child" :depth="depth + 1" @onClick="(node) => $emit('onClick', node)" />
    </ul>
</div>
</template>

<script>
export default {
    name: 'TreeBrowser',
    props: {
        node: Object,
        depth: {
            type: Number,
            default: 0,
        }
    },
    data() {
        return {
            expanded: false
        }
    },
    methods: {
        nodeClicked() {
            this.expanded = !this.expanded;
            if (!this.hasChildren) {
                this.$emit('onClick', this.node);
            }
        },
        getStyle(node) {
            let color = 'red';
            if (!node.children) {
                color = 'blue';
            }
            return {
                color,
            }
        }
    },
    computed: {
        hasChildren() {
            return this.node.children;
        }
    }
}
</script>

<style scoped>
.node {
    text-align: left;
    font-size: 18px;
}

.type {
    margin-right: 10px;
}

</style>
