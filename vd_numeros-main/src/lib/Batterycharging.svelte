<script>
  import * as d3 from "d3"

  export let numbers = []

  function alturaColBattery(n) {
    let scale = d3
      .scaleLinear()
      .domain([0, d3.max(numbers)])
      .range([0, 100])
    return scale(n)
  }

</script>


<div class="battery-container">
  {#each numbers as n}
  <div>
    <div class="column-wrapper">
      <div class="column-battery" style="height: {alturaColBattery(n)}%;"></div>
      <img class="battery" src="./images/bateria-vacia.png" alt="" style="height: 231px;">
      <img class="rayo" src="./images/destello.png" alt=""style="height: 60px;">
    </div>
    <p class="number">{n}</p>
  </div>
  {/each}
</div>

<style>
  .battery-container {
    display: flex;
  }
  .column-wrapper {
    position: relative;
    width: 160px;
    height: 200px;
  }
  .column-battery {
    position: absolute;
    width: 115px;
    left: 27%;
    right: 25%;
    bottom: 0;
    background-color: rgb(42, 180, 53);
  }
  .battery {
    position: absolute;
    width: 112%;
    bottom: -10px;
  }
  .rayo {
    position: absolute;
    left: 82px;
    bottom: 72px;
  }
  .number {
    position: relative;
    font-size: larger;
    font-weight: 500;
    text-align: center;
    left: 12px;
    color: black;
  }
</style>