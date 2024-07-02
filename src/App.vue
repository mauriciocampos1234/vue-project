  <template>
    <div>
      <input type="number" v-model="num1" />      
      <input type="number" v-model="num2" />
      <select v-model="operation">
        <option value="+">Soma</option>
        <option value="-">Subtração</option>
        <option value="*">Multiplicação</option>
        <option value="/">Divisão</option>
      </select>
      <p>Resultado: {{ result }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        num1: 0,
        num2: 0,
        operation: "+",
        result: 0
      };
    },
    watch: {
      num1() {
        this.calculate();
      },
      num2() {
        this.calculate();
      },
      operation() {
        this.calculate();
      }
    },
    methods: {
      calculate() {
        switch (this.operation) {
          case "+":
            this.result = this.num1 + this.num2;
            break;
          case "-":
            this.result = this.num1 - this.num2;
            break;
          case "*":
            this.result = this.num1 * this.num2;
            break;
          case "/":
            this.result = this.num1 / this.num2;
            break;
        }
      }
    }
  };
  </script>
  
