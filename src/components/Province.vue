<template>
    <div>
        <div id="province" style="width: 600px; height: 600px"></div>
    </div>
</template>

<script>
import * as echarts from "echarts";

export default {
    name: "Province",
    props: {
        fileName: String,
    },
    data() {
        return {
            option: {
                series: [
                    {
                        name: "省份数据",
                        type: "map",
                        map: "province",
                        data: [],
                    },
                ],
            },
        };
    },
    mounted() {
        this.initData();
    },
    methods: {
        initData() {
            try {
                const provinceJSON = require("../data/province/" +
                    this.fileName);
                const myChart = echarts.init(
                    document.getElementById("province")
                );
                echarts.registerMap("province", provinceJSON);
                myChart.setOption(this.option);
                myChart.on("click", () => this.$emit("toMap"));
            } catch (e) {
                alert(`暂无${this.fileName}数据`);
                this.$emit("toMap");
            }
        },
    },
};
</script>

<style scoped rel="stylesheet/scss" lang="scss"></style>
