<script lang="ts">
import '../app.css'
  let display: string = "";

  const handleClick = (value: string): void => {
    display += value;
  };
</script>

<svelte:head>
  <title>Calculator in Svelte</title>
</svelte:head>

<div class="container">
  <div class="calculator">
    <form>
      <div class="display">
        <input type="text" name="display" bind:value={display} />
      </div>
      <div>
        <input type="button" value="AC" on:click={() => display = ""} class="operator" />
        <input type="button" value="DE" on:click={() => display = display.toString().slice(0, -1)} class="operator" />
        <input type="button" value="." on:click={() => handleClick(".")} class="operator" />
        <input type="button" value="/" on:click={() => handleClick("/")} class="operator" />
      </div>
      <div>
        <input type="button" value="7" on:click={() => handleClick("7")} />
        <input type="button" value="8" on:click={() => handleClick("8")} />
        <input type="button" value="9" on:click={() => handleClick("9")} />
        <input type="button" value="*" on:click={() => handleClick("*")} class="operator" />
      </div>
      <div>
        <input type="button" value="4" on:click={() => handleClick("4")} />
        <input type="button" value="5" on:click={() => handleClick("5")} />
        <input type="button" value="6" on:click={() => handleClick("6")} />
        <input type="button" value="-" on:click={() => handleClick("-")} class="operator" />
      </div>
      <div>
        <input type="button" value="1" on:click={() => handleClick("1")} />
        <input type="button" value="2" on:click={() => handleClick("2")} />
        <input type="button" value="3" on:click={() => handleClick("3")} />
        <input type="button" value="+" on:click={() => handleClick("+")} class="operator" />
      </div>
      <div>
        <input type="button" value="00" on:click={() => handleClick("00")} />
        <input type="button" value="0" on:click={() => handleClick("0")} />
        <input type="button" value="=" class="equal operator" on:click={() => display = eval(display)}  />
      </div>
    </form>
  </div>
</div>
