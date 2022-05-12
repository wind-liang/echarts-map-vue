<template>
    <div>
        <Province
            v-if="showProvince"
            :fileName="fileName"
            @toMap="toMap"
        ></Province>

        <Map v-else @toProvince="toProvince"></Map>
    </div>
</template>

<script>
import Province from "./Province.vue";
import Map from "./Map.vue";

export default {
    name: "HelloWorld",
    components: {
        Province,
        Map,
    },
    data() {
        return {
            showProvince: false,
            fileName: null,
        };
    },
    methods: {
        toProvince({ fileName } = {}) {
            this.fileName = fileName;
            this.showProvince = true;
        },
        toMap() {
            this.showProvince = false;
        },
    },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
