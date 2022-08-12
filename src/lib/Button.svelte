<script>
  export let value;
  export let currentDisplay;
  export let operator;
  export let operandA;
  export let operandB;
  export let tmp;
  export let isCommaOnA = false;
  export let isCommaOnB = false;

  const audio = new Audio("/button.mp3");

  function handleClick() {
    audio.play();
    if (value === "C") {
      currentDisplay = "";
      operandA = "";
      operandB = "";
      operator = "";
      tmp = "";
      isCommaOnA = false;
      isCommaOnB = false;
    } else if (value === "=") {
      if (operandB) {
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
          case "%":
            currentDisplay = operandA % operandB;
            break;
        }
      }
      operandA = currentDisplay;
      operator = "";
      tmp = "";
      operandB = "";
      isCommaOnB = false;
      if (!(currentDisplay + "").includes(".")) {
        isCommaOnA = false;
      }
    } else if (value === "!") {
      if (operandB) {
        operandB = operandB * -1;
        currentDisplay = operandB;
        console.log(operandB);
      } else {
        currentDisplay = currentDisplay * -1;
        console.log(operandA);
      }
    } else if (value === ".") {
      if (!tmp) {
        if (!isCommaOnA) {
          isCommaOnA = true;
          currentDisplay += ".";
        }
      } else {
        if (!isCommaOnB) {
          isCommaOnB = true;
          tmp += ".";
        }
      }
    } else if (typeof value !== "number") {
      if (!operator) {
        operator = value;
        operandA = currentDisplay;
      } else {
        if (operandB) {
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
            case "%":
              currentDisplay = operandA % operandB;
              break;
          }
          operandA = currentDisplay;
          operator = value;
          tmp = "";
          operandB = "";
          isCommaOnB = false;
          if (!(currentDisplay + "").includes(".")) {
            isCommaOnA = false;
          }
        }
        operator = value;
      }
    } else {
      if (!operator) {
        currentDisplay += "" + value;
        currentDisplay = +currentDisplay;
      } else {
        currentDisplay = "";
        tmp = tmp + value;
        currentDisplay = tmp;
        operandB = +tmp;
      }
    }
  }
</script>

<button
  class="btn"
  on:click={handleClick}
  class:active={operator === value && !operandB}
>
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
    transition: all 0.2s;
  }

  .btn:hover {
    background-color: #999;
  }

  .btn:active {
    background-color: #777;
    box-shadow: 0 0 1px 1px rgba(0, 0, 0, 0.5);
    border: 1px solid #888;
  }

  .active {
    background-color: orange;
  }

  .active:hover {
    background-color: orangered;
  }

  .active:active {
    background-color: orange;
  }
</style>
