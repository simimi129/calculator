<script>
  import Button from "./Button.svelte";
  import Display from "./Display.svelte";

  let currentDisplay = "";
  let operator;
  let operandA;
  let operandB;
</script>

<div class="calculator">
  <Display {currentDisplay} />
  <div class="buttons">
    <div class="row">
      <Button
        value={"C"}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
      <Button
        value={"!"}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
      <Button
        value={"%"}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
      <Button
        value={"/"}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
    </div>
    <div class="row">
      <Button
        value={7}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
      <Button
        value={8}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
      <Button
        value={9}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
      <Button
        value={"*"}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
    </div>
    <div class="row">
      <Button
        value={4}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
      <Button
        value={5}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
      <Button
        value={6}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
      <Button
        value={"-"}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
    </div>
    <div class="row">
      <Button
        value={1}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
      <Button
        value={2}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
      <Button
        value={3}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
      <Button
        value={"+"}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
    </div>
    <div class="row">
      <Button
        value={0}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
      <Button
        value={","}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
      <Button
        value={"="}
        bind:currentDisplay
        bind:operator
        bind:operandA
        bind:operandB
      />
    </div>
  </div>
</div>

<style>
  .row {
    display: flex;
    gap: 20px;
    height: 100%;
  }

  .buttons {
    display: flex;
    flex-direction: column;
    gap: 20px;
    padding: 10px;
    width: 100%;
    height: 100%;
    background-color: #999;
    border-radius: 30px;
    border: 1px solid #666;
    box-shadow: inset 1px 1px 10px 5px rgba(0, 0, 0, 0.5);
  }

  .calculator {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
    padding: 20px;
    min-width: 300px;
    width: 30vw;
    min-height: 400px;
    height: 40vw;
    background: linear-gradient(to bottom right, #222, #111);
    box-shadow: 2px 2px 10px 2px rgba(0, 0, 0, 0.5);
    border: 1px solid #333;
    border-radius: 20px;
  }
</style>
