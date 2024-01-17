<script lang="ts" setup>
    import FloatingFooter from "./components/FloatingFooter.vue";
    import VueLogo from "./components/VueLogo.vue";
</script>

<template>
    <header>
        <VueLogo />
    </header>
    <nav>
        <RouterLink :to="{ name: 'home' }">
            Home
        </RouterLink> |
        <RouterLink :to="{ name: 'about' }">
            About
        </RouterLink>
    </nav>
    <main>
        <RouterView v-slot="context">
            <Transition name="fade" mode="out-in">
                <Component :is="context.Component" :key="context.route.path" />
            </Transition>
        </RouterView>
    </main>
    <FloatingFooter />
</template>

<style lang="scss">
    @import "@/assets/scss/index";

    #app
    {
        align-items: center;
        background-color: $app-slightly-off-white;
        box-shadow: 0px 0px 8px 0px rgba(0, 0, 0, 0.5);
        display: flex;
        flex-direction: column;
        justify-content: center;
        margin-bottom: 56px;
        min-height: 100vh;
        text-align: center;

        & > .fade-enter-from,
        & > .fade-leave-to
        {
            opacity: 0;
        }
        & > .fade-enter-active,
        & > .fade-leave-active
        {
            transition: opacity $app-transition-duration $app-transition-timing;
        }
        & > .fade-enter-to,
        & > .fade-leave-from
        {
            opacity: 1;
        }

        & > header
        {
            padding: 2.5rem;
            padding-bottom: 1.5rem;
        }
        & > nav
        {
            padding: 1rem;
        }
        & > main
        {
            flex: 1;
        }
    }
</style>
