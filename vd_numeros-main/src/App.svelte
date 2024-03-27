<script>
  import * as d3 from "d3"
  import Batterycharging from "./lib/Batterycharging.svelte"
  let numbers = [10, 25, 33, 62, 75, 100]
  let numbersDivided5 = numbers.map(n => Math.floor(n / 5))

  function altura(n) {
    let scale = d3
      .scaleLinear()
      .domain(d3.extent(numbers))
      .range([15, 225])
    return scale(n)
  }
</script>

<main>

  <h1 class="headline">CARGA DE LA BATERIA</h1>
  <Batterycharging numbers={numbers}/>

</main>

<style>
  :global(body){
    background-color: white;
  }
  .headline {
    position: relative;
    font-family:Times;
    font-weight: lighter;
    text-align: center;
    margin-top: 100px;
    bottom: 75px;
    color: black;
  }

</style>