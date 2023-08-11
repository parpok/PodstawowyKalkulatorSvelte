<script lang="ts">

let num1: number;
let num2: number;
let operator: string;
let result: number;

    function dzialanie(n1: number, n2: number, operator: string): number {
        switch (operator) {
            case "+":
                return n1 + n2;

            case "-":
                return n1 - n2;

            case "*"|| "x":
                return n1 * n2;

            case "/"|| ":":
                return n1 / n2;

            default:
                throw console.error("Brak typu działania");
        }
    }

function handleClick() {
 result = dzialanie(num1, num2, operator);
}
  </script>
  
  <main>
    <form>
      <input type="number" bind:value={num1} placeholder="Number 1">

        <select bind:value={operator}>
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">* lub x mnożenie</option>
            <option value="/">/ lub : dzielenie</option>
        </select>

      <input type="number" bind:value={num2} placeholder="Number 2">
    </form>
  
    <button on:click={handleClick}>Oblicz</button>
    <br>
    
    {#if result !== undefined}
        <p2>Wynik to: {result}</p2>
    {/if}
  </main>

  <style>

    button{
        border: none;
        text-align: center;
        text-decoration: none;
    }

  </style>