<script>
// import swipe from 'svelte-swipeable';
import { Animations } from 'svelte-swipeable';
  let direction = 'any';
  let willReturn = false;
  let stiffness = 0.2;
  let damping = 0.6;
  let momentum = 0.2;
  let generatedCode;

  // let options = {
  //   threshX: 100,
  //   threshY: 75,
  // }

  // const handleSwipeUp = (event) => {
  //   console.log(event);

  //   if(event.detail.direction.y === 'up') {
  //     willReturn = false;
  //     momentum = 5;
  //   }
  // }
  function myFunction() {
  generatedCode.select();
  document.execCommand('copy');
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Roboto&display=swap');
  :global(body) {
    font-family: 'Roboto', sans-serif;
  }
  .title {
    width: 100%;
    text-align: center;
    margin: 100px 0;
    font-size: 50px;
  }
  .box {
    background-image: linear-gradient(to right top, #ffc342, #ffca52, #ffd061, #ffd670, #ffdc7e);
    width: 300px;
    height: 100px;
    border-radius: 5px;
    padding: 10px;
    box-shadow: 0 0 40px 5px rgba(0, 0, 0, 0.212);
  }
  .example-box {
    margin: 100px;
  }
  .container {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-between;
    margin: 100px;
    padding: 200px 30px;
    background-color: rgb(226, 226, 226);
    box-shadow: 0 0 40px 10px rgb(224, 224, 224);
  }
  .input {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 20px 0;
  }
  .settings {
    width: 400px;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 40px 10px rgb(206, 206, 206);
  }
  .slider {
    -webkit-appearance: none;  /* Override default CSS styles */
    appearance: none;
    width: 60%; /* Full-width */
    height: 25px; /* Specified height */
    background: #d3d3d3; /* Grey background */
    outline: none; /* Remove outline */
    opacity: 0.7; /* Set transparency (for mouse-over effects on hover) */
    -webkit-transition: .2s; /* 0.2 seconds transition on hover */
    transition: opacity .2s;
  }

  /* Mouse-over effects */
  .slider:hover {
    opacity: 1; /* Fully shown on mouse-over */
  }

  /* The slider handle (use -webkit- (Chrome, Opera, Safari, Edge) and -moz- (Firefox) to override default look) */
  .slider::-webkit-slider-thumb {
    -webkit-appearance: none; /* Override default look */
    appearance: none;
    width: 25px; /* Set a specific slider handle width */
    height: 25px; /* Slider handle height */
    background-image: linear-gradient(to right top, #f0b83f, #ffca52); /* Green background */
    cursor: pointer; /* Cursor on hover */
  }

  .slider::-moz-range-thumb {
    width: 25px; /* Set a specific slider handle width */
    height: 25px; /* Slider handle height */
    background-image: linear-gradient(to right top, #ebb339, #ffca52); /* Green background */
    cursor: pointer; /* Cursor on hover */
  }

  .checkbox {
    width: 25px;
    height: 25px;
    cursor: pointer; 
  }
.select {
    display: block;
    font-size: 15px;
    font-weight: 500;
    line-height: 1.3;
    padding: .6em 1.4em .5em .8em;
    width: 60%;
    max-width: 100%; 
    box-sizing: border-box;
    margin: 0;
    -moz-appearance: none;
    -webkit-appearance: none;
    border-radius: 0;
    border-color: transparent;
    appearance: none;
    background-image: url('data:image/svg+xml;charset=US-ASCII,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22292.4%22%20height%3D%22292.4%22%3E%3Cpath%20fill%3D%22%23007CB2%22%20d%3D%22M287%2069.4a17.6%2017.6%200%200%200-13-5.4H18.4c-5%200-9.3%201.8-12.9%205.4A17.6%2017.6%200%200%200%200%2082.2c0%205%201.8%209.3%205.4%2012.9l128%20127.9c3.6%203.6%207.8%205.4%2012.8%205.4s9.2-1.8%2012.8-5.4L287%2095c3.5-3.5%205.4-7.8%205.4-12.8%200-5-1.9-9.2-5.5-12.8z%22%2F%3E%3C%2Fsvg%3E'),
      linear-gradient(to bottom, #d6d6d6 0%,#d6d6d6 100%);
    background-repeat: no-repeat, repeat;
    background-position: right .7em top 50%, 0 0;
    background-size: .65em auto, 100%;
}
.select::-ms-expand {
    display: none;
}
.select:hover {
  background-image: url('data:image/svg+xml;charset=US-ASCII,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22292.4%22%20height%3D%22292.4%22%3E%3Cpath%20fill%3D%22%23007CB2%22%20d%3D%22M287%2069.4a17.6%2017.6%200%200%200-13-5.4H18.4c-5%200-9.3%201.8-12.9%205.4A17.6%2017.6%200%200%200%200%2082.2c0%205%201.8%209.3%205.4%2012.9l128%20127.9c3.6%203.6%207.8%205.4%2012.8%205.4s9.2-1.8%2012.8-5.4L287%2095c3.5-3.5%205.4-7.8%205.4-12.8%200-5-1.9-9.2-5.5-12.8z%22%2F%3E%3C%2Fsvg%3E'),
    linear-gradient(to bottom, #d3d3d3 0%,#d3d3d3 100%);
  cursor: pointer;
}
.select:focus {
    color: #222; 
    outline: none;
}

.generated {
  display: flex;
  flex-direction: column;
  padding: 10px;

}

  .copy-button {
    padding: 10px 0;
    background-image: linear-gradient(to right top, #ffc342, #ffca52, #ffd061, #ffd670, #ffdc7e);
    border-color: transparent;
    color: black;
    font-size: 15px;
    border-radius: 5px;
  }

  .text-area {
    margin-top: 10px;
    resize: none;
    font-size: 15px;
    border-radius: 5px;
    border-color: transparent;
    line-height: 20px;
    background-color: #d6d6d6;
    box-shadow: 0 0 40px 10px rgb(224, 224, 224);
  }

</style>
<h1 class="title">Svelte-Swipeable</h1>
<div class="container">

    <Animations direction={direction} stiffness={stiffness} damping={damping} willReturn={willReturn} momentum={momentum}>
      <div class="box">
        Move me!
      </div>
    </Animations>
    <div class="settings">
      <div class="input">
        Direction: 
        {direction}
        <select id="direction" name="direction" bind:value={direction} class="select">
          <option value="any" class="option">any</option>
          <option value="horizontal" class="option">horizontal</option>
          <option value="vertical" class="option">vertical</option>
          <option value="up" class="option">up</option>
          <option value="down" class="option">down</option>
          <option value="left" class="option">left</option>
          <option value="right" class="option">right</option>
        </select>
      </div>

      <div class="input">
        Stiffness: 
        {stiffness}
        <input type="range" min="0" max="1" step="0.1" bind:value={stiffness} class="slider" id="stiffness">
      </div>
      <div class="input">
        Damping: 
        {damping}
        <input type="range" min="0" max="1" step="0.1" bind:value={damping} class="slider" id="damping">
      </div>
      <div class="input">
        Momentum: 
        {momentum}
        <input type="range" min="0" max="1" step="0.1" bind:value={momentum} class="slider" id="momentum">
      </div>
      <div class="input">
        Will Return: 
        {willReturn}
        <input type="checkbox" bind:checked={willReturn} class="checkbox" id="willReturn">
      </div>
      <div class="generated">
        <button class="copy-button" on:click={myFunction}>Copy to Clipboard!</button>
        <textarea bind:this={generatedCode} readonly class="text-area" rows="13" cols="40">
          &lt;Animations 
              direction={direction} 
              stiffness={stiffness} 
              damping={damping} 
              willReturn={willReturn} 
              momentum={momentum} &gt

              &lt;div&gt Move me! &lt;/ div&gt

          &lt;/ Animations&gt       
        </textarea>
      </div>
    </div>
</div>

  <!-- <Animations
    options={options}
    direction={'vertical'} 
    stiffness={0.02} 
    damping={0.4}
    momentum={momentum} 
    willReturn={willReturn} 
    onSwipeUp={handleSwipeUp}
    >
    <div class="box">
      Animations Up!
    </div>
  </Animations> -->

  <Animations direction={'horizontal'} stiffness={0.01} damping={0} willReturn={false} momentum={1}>
    <div class="box example-box">
      Hotizontal
    </div>
  </Animations>
  <Animations direction={'any'} stiffness={0.2} damping={0} willReturn={false} momentum={0.3}>
    <div class="box example-box">
      Any Direction
    </div>
  </Animations>
  <Animations direction={'up'} stiffness={0.1} damping={0.7} willReturn={false} momentum={0.5}>
    <div class="box example-box">
      Up
    </div>
  </Animations>
  <Animations direction={'down'} stiffness={0.1} damping={0.7}>
    <div class="box example-box">
      Down  
    </div>
  </Animations>
  <Animations direction={'right'} stiffness={0.1} damping={0.7}>
    <div class="box example-box">
      Right
    </div>
  </Animations>
  <Animations direction={'left'} stiffness={0.1} damping={0.5}>
    <div class="box example-box">
      Left
    </div>
  </Animations>

