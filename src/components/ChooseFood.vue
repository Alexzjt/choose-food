<template>
    <div class="inner-content">
        <h3>用餐人数：
            <a-select placeholder="请选择" style="width: 120px" @change="handleChange">
                <!--<a-select-option value="1">1</a-select-option>-->
                <a-select-option value="2">2</a-select-option>
                <a-select-option value="3">3</a-select-option>
                <a-select-option value="4">4</a-select-option>
                <a-select-option value="5">5</a-select-option>
            </a-select>
<!--            <a-button type="primary" shape="circle" icon="search" @click="handleChange"></a-button>-->
        </h3>
        <h1 class="result">{{result}}</h1>
    </div>
</template>

<script>
    export default {
        name: "ChooseFood",
        data() {
            return {
                result: ""
            }
        },
        methods: {
            handleChange(value) {
                this.generateFood(value);
            },
            generateFood(value) {
                //常量定义
                var vegetableDishes = ['炒时蔬（豌豆尖/油麦菜/空心菜/油菜）', '麻婆豆腐', '干煸豆角', '土豆丝', '西红柿炒鸡蛋', '炒花菜（西蓝花）', '炒莲白', '韭菜炒蛋', '炒藕片'];
                var meatDishes = ['回锅肉', '丝瓜番茄丸子汤', '炒腊肉', '蒜蓉粉丝虾', '糖醋排骨', '水煮肉片', '炖牛肉（羊肉）', '炒嫩牛肉', '肝腰合炒', '炒兔肉', '西红柿牛腩', '清蒸鲈鱼'
                    , '水煮鱼', '土豆烧鸭子（排骨/五花肉）', '炒火腿肠（豆类/炝炒）', '炒鱿鱼', '麻辣香锅', '火锅', '可乐鸡翅', '自制卤菜', '炒肉', '宫保鸡丁'];
                var vegetableNumber = value / 2 >> 0;
                var meatNumber = value - vegetableNumber;
                this.result = `为您推荐${meatNumber}荤${vegetableNumber}素\n`;
                for (let count = 0; count < meatNumber; count++) {
                    this.result += `${meatDishes[this.randomNum(0, meatDishes.length - 1)]}\n`;
                }
                for (let count = 0; count < vegetableNumber; count++) {
                    this.result += `${vegetableDishes[this.randomNum(0, vegetableDishes.length - 1)]}\n`;
                }
            },
            randomNum(minNum, maxNum) {
                switch (arguments.length) {
                    case 1:
                        return parseInt(Math.random() * minNum + 1, 10);
                        break;
                    case 2:
                        return parseInt(Math.random() * (maxNum - minNum + 1) + minNum, 10);
                        break;
                    default:
                        return 0;
                        break;
                }
            }
        }
    }
</script>

<style scoped>
    .inner-content {
        position: absolute;
        top:44%;
        left:37%;
        width: 500px;
        height: 400px;
        text-align: center;
    }

    .result {
        white-space: pre;
    }
</style>
