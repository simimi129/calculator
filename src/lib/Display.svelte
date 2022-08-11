<script>
  export let currentDisplay;
</script>

<div class="display">
  {currentDisplay}
</div>

<style>
  .display {
    overflow-x: scroll;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    color: white;
    font-size: 10rem;
    text-shadow: 2px 2px 2px rgba(0, 0, 0, 0.3);
    width: 100%;
    height: 200px;
    background-color: #555;
    border-radius: 30px;
    border: 1px solid #555;
    box-shadow: inset 1px 1px 5px 2px rgba(0, 0, 0, 0.5);
    padding: 0 10px;
  }

  .display::-webkit-scrollbar {
    display: none;
  }
</style>
