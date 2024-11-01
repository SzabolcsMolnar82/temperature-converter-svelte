<script lang="ts">

  class Temperature {
    #c = $state(0)
    #f = $state(0)

    get c() {
      return this.#c
    }

    set c(c) {
      this.#c = c
      this.#f = c * 9 / 5 + 32
    }

    get f() {
      return this.#f
    }

    set f(f) {
      this.#c = (f - 32) * 5 / 9
    }
  }

  const temperature = new Temperature()



</script>

<div>
  <input type="number" bind:value={temperature.c} />Celsius=
  <input type="number" bind:value={temperature.f} />Fahrenheit
</div>

<style>
  div {
    font-size: 30px;
    color: white;
  }
  input[type="number"] {
    max-width: 10ch;
    text-align: center;
    font-size: 25px;
    font-family: 'Times New Roman', Times, serif;
    border-radius: 30px;
  }
</style>