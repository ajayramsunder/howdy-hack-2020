<template>
    <el-select v-model="selected" placeholder="Choose your stuff" style="float:left">
        <el-option
        v-for="option in options"
        :key="option"
        :label="option"
        :value="option">
        </el-option>
    </el-select>
</template>

<script>
export default {
    data () {
        return {
            selected: '',
            options: ['Chris the Cadet', 'Money Manziel', 'Fratboy RayJay']
        }
    },
    watch: {
        selected: function() {
            this.$emit('selected-value',this.selected)
        }
    },
}
</script>

