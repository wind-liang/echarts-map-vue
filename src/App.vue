<template>
    <div id="app">
        <MapProvince />
    </div>
</template>

<script>
import MapProvince from "./components/MapProvince";

export default {
    name: "App",
    components: {
        MapProvince,
    },
};
</script>

<style>
#app {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 80vh;
}
</style>
