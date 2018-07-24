<template lang="pug">
    div.desco-input-tags
        el-tag(
            v-for="tag in tags" closable
            :key="tag" :disable-transitions="!transitions" @close="removeTag(tag)"
        )
            |{{tag}}
        el-input.input-new-tag(
            v-if="inputVisible" v-model="inputValue" ref="saveTagInput" size="mini"
            @keyup.enter.native="addTag", @blur="inputBlur"
        )
        el-button.button-new-tag(v-else="" size="small" @click="showInput") {{newTagTxt}}

</template>

<script>
import Vue from "vue"
import ElementUI from "element-ui"
import "element-ui/lib/theme-chalk/index.css"

Vue.use(ElementUI)

export default {
    name: "DescoInputTags",
    props: {
        value: String,
        newTagTxt: { type: String, default: '+ Tag' },
        separatorCharacter: { type: String, default: ';' },
        addOnBlur: { type: Boolean, default: true },
        allowRepeat: { type: Boolean, default: false },
        max: { type: Number, default: 0 },
        transitions: { type: Boolean, default: true },
    },
    data () {
        return {
            tags: [],
            inputVisible: false,
            inputValue: ''
        }
    },
    methods: {
        fetch () {
            this.tags = this.value ? this.value.split(this.separatorCharacter) : []
        },
        showInput () {
            this.inputVisible = true

            this.$nextTick(_ => { this.$refs.saveTagInput.$refs.input.focus() })
            this.$emit('show-input')
        },
        inputBlur () {
            this.$emit('blur', this.inputValue)

            if(this.addOnBlur) this.addTag()
        },
        addTag () {
            const breakRepeat = !this.allowRepeat && this.tags.indexOf(this.inputValue) !== -1
            const breakMax = this.max > 0 && this.tags.length + 1 > this.max

            if (breakRepeat) this.$emit('break-repeat', this.inputValue)
            if (breakMax) this.$emit('break-max', this.inputValue)

            if (this.inputValue && !breakRepeat && !breakMax ) {
                this.tags.push(this.inputValue)

                this.$emit('add', this.inputValue)
                this.$emit('change', this.inputValue)
            }

            this.inputVisible = false
            this.inputValue = ''
        },
        removeTag (tag) {
            this.tags.splice(this.tags.indexOf(tag), 1)

            this.$emit('remove', tag)
            this.$emit('change', tag)
        },
    },
    mounted () {
        this.fetch()
    },
    watch: {
        value () {
            this.fetch()
        },
        tags () {
            this.$emit('input', this.tags.join(this.separatorCharacter))
        }
    }
}
</script>

<style lang="scss">
    div.desco-input-tags {
        .el-tag {
            & + .el-tag {
                margin-left: 10px;
            }

            & + .button-new-tag,
            & + .input-new-tag {
                margin-left: 10px;
            }

        }

        .button-new-tag {
            height: 32px;
            line-height: 30px;
            padding-top: 0;
            padding-bottom: 0;
        }

        .input-new-tag {
            width: 90px;
            vertical-align: bottom;
        }
    }
</style>