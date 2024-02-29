<script lang="ts" setup>
    import FloatingFooter from "@/components/globals/FloatingFooter.vue";
    import NavigationBar from "@/components/globals/NavigationBar.vue";

    import VueLogo from "@/components/VueLogo.vue";
</script>

<template>
    <div class="default-layout">
        <header>
            <VueLogo />
        </header>
        <NavigationBar />
        <slot></slot>
        <FloatingFooter />
    </div>
</template>

<style lang="scss" scoped>
    @use "@/assets/scss/variables";

    .default-layout
    {
        background-color: variables.$slightly-off-white;
        border-bottom: 1px solid rgba(0, 0, 0, 0.25);
        box-shadow: 0px 0px 8px 0px rgba(0, 0, 0, 0.5);
        flex: 1;
        margin-bottom: 104px;
        min-height: 100svh;
        padding-top: 64px;
        text-align: center;
        width: 100%;
    }
</style>
