<script>
  export let value;
  export let currentDisplay;
  export let operator;
  export let operandA;
  export let operandB;

  function handleClick() {
    if (value === "C") {
      currentDisplay = "";
      operandA = "";
      operandB = "";
      operator = "";
    } else if (value === "=") {
      switch (operator) {
        case "+":
          currentDisplay = operandA + operandB;
          break;
        case "-":
          currentDisplay = operandA - operandB;
          break;
        case "*":
          currentDisplay = operandA * operandB;
          break;
        case "/":
          currentDisplay = operandA / operandB;
          break;
      }
      operandA = currentDisplay;
    } else if (typeof value !== "number") {
      if (!operator) {
        operator = value;
        operandA = currentDisplay;
      } else {
        operator = value;
      }
    } else {
      if (!operator) {
        currentDisplay += "" + value;
        currentDisplay = +currentDisplay;
      } else {
        currentDisplay = "";
        currentDisplay += "" + value;
        currentDisplay = +currentDisplay;
        operandB = currentDisplay;
      }
    }
    console.log(operator);
    console.log(operandA);
    console.log(operandB);
  }
</script>

<button class="btn" on:click={handleClick} class:active={operator === value}>
  {value}
</button>

<style>
  .btn {
    width: 100%;
    height: 100%;
    font-size: 5rem;
    border-radius: 20px;
    border: 1px solid #999;
    box-shadow: 1px 1px 5px 1px rgba(0, 0, 0, 0.5);
    background-color: #888;
  }

  .active {
    background-color: orange;
  }
</style>
