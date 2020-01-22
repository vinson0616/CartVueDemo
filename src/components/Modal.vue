<template>
    <div>
        <div class="md-modal modal-msg md-modal-transition" :class="{'md-show': ShowModal}">
            <div class="md-modal-inner">
                <div class="md-top">
                    <button class="md-close" @click="closeModal">关闭</button>
                </div>
                <div class="md-content">
                    <div class="confirm-tips">
                       <slot name="message"></slot>
                    </div>
                    <div class="btn-wrap">
                        <slot name="btnGroup"></slot>
                    </div>
                </div>
            </div>
        </div>
        <div class="md-overlay" v-if="ShowModal" @click="closeModal"></div>
    </div>

</template>

<script>
    export default {
        name: 'modal',
        props:['ShowModal'],
        methods:{
            closeModal(){
                //调用父组件调用
                this.$emit('close')
            }
        }
    }
</script>

<style scoped>

</style>