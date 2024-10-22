<template>
    <header class="p-5 mb-4 mt-4 text-center bg-light text-dark">
        <h1>
            <p class="fw-bold">Calculadora vue</p>
        </h1>
    </header>
    <div class="calculator text-center">
        <div class="inputs bg-light">
            <input type="number" v-model.number="number1" @input="compute" placeholder="Número 1" />
            <select v-model="operation" @change="compute">
                <option class="border border-primary"  value="+">+</option>
                <option value="-">-</option>
                <option value="*">*</option>
                <option value="/">/</option>
            </select>
            <input type="number" v-model.number="number2" @input="compute" placeholder="Número 2" />
        </div>

        <div class="result">
            Resultado: {{ result }}
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            number1: 0,
            number2: 0,
            operation: '+',
            result: 0,
        };
    },
    methods: {
        compute() {
            switch (this.operation) {
                case '+':
                    this.result = this.number1 + this.number2;
                    break;
                case '-':
                    this.result = this.number1 - this.number2;
                    break;
                case '*':
                    this.result = this.number1 * this.number2;
                    break;
                case '/':
                    this.result = this.number2 !== 0 ? this.number1 / this.number2 : 'Erro';
                    break;
            }
        }
    },
    mounted() {
        
        this.compute();
    }
};
</script>

