<template>
    <div class="layout" :data-kontent-project-id="projectId" data-kontent-language-codename="en-US">
        <slot />
    </div>
</template>

<script lang="ts" setup>
    import { useNuxtApp } from '#app'
    const projectId = useNuxtApp().$config.kontent.projectId
</script>

<style lang="scss">

@import "../assets/scss/variables";
@import "../assets/scss/mixins";

.layout {
    max-width: $layout-width;
    margin-left: auto;
    margin-right: auto;

    display: flex;
    flex-direction: column;
}

.layout > div {
  display: flex;
  flex-direction: row;
}

.layout > div > div {
    margin: 0 auto;
}
    
@include breakpoint-sm {
    .layout {
        flex-direction: row;
    }
}
</style>