<script>
  // @ts-ignore
  import svelteLogo from "./assets/svelte.svg";
  import Counter from "./lib/Counter.svelte";
  import Circles from "./lib/Circles.svelte";
  import Rectangles from "./lib/Rectangles.svelte";
  import Scrolly from "./lib/Scrolly.svelte";
  import Intro from "./lib/Intro.svelte";
  import Arrow from "./lib/Arrow.svelte";

  // let shape = 'circles'

  // const shapeShift=(s)=>{
  //   shape = s
  //   console.log(shape)
  // }

  let value;
  const steps = [
    "<p>Firstly, before we can quantify the cost of a dollar in US prisons, we need to understand wages earned by incarcerated people in the US.<br></br> Different prison jobs are compensated at various rates across states. Regardless, we can use a <span style = 'color: #7695c4; font-weight: 700'>median wage</span> for prison labor as a state-based metric for this analysis.</p>",
    "<p>Here, for example, we can see that the state of <span style = 'color: #ff9f3f; font-weight: 700'>Nevada</span> has the highest median prison wage.</p>",
    "<p>But regardless of the fact that <span style = 'color: #ff9f3f; font-weight: 700'>Nevada</span> ranks highest in median prison wages, incarcerated workers in this state are compensated <span style = 'color: #7695c4; font-weight: 700'>7.80 $/hour</span> less than the government mandated minimum wage of <span style = 'color: #7695c4; font-weight: 700'>10.50 $/hour</span>.</p>",
    "<p>Alternatively, while the government mandated minimum wages in <span style = 'color: #ff9f3f; font-weight: 700'>Arkansas</span>, <span style = 'color: #ff9f3f; font-weight: 700'>Georgia</span>, and <span style = 'color: #ff9f3f; font-weight: 700'>Texas</span> are <span style = 'color: #7695c4; font-weight: 700'>11.00 $/hour</span>, <span style = 'color: #7695c4; font-weight: 700'>7.25 $/hour</span>, and <span style = 'color: #7695c4; font-weight: 700'>7.25 $/hour</span> respectively,</p>",
    "<p>these states don’t compensate incarcerated workers at all for their labor.</p>",
    "<p>Given this information, we can try to understand what a dollar costs in the US prison system in terms of <span style = 'color: #7695c4; font-weight: 700'>labor</span>.<br></br> In each state, how many hours of <span style = 'color: #7695c4; font-weight: 700'>labor</span> equate to <span style = 'color: #7695c4; font-weight: 700'>$1.00</span> in prison wages? </p>",
    "<p>Given the fact that people in Arkansas, Georgia, and Texas aren’t financially compensated at all for their prison labor, folks incarcerated in these states can’t even earn a dollar.</p>",
    "<p>  </p>",
    "<p>But in considering other states, and in terms of labor conducted,</p>",
    "<p>we can see that a dollar costs the most in Alabama.</p>",
    "<p>With a median prison wage of 0.12 $/hour, incarcerated people in Alabama must conduct 8.33 hours of labor at the median prison wage in order to earn a single dollar.</p>",
    "<p>  </p>",
    "<p>On the other hand,</p>",
    "<p>this same $1.00 is least expensive in the state of Nevada.</p>",
    "<p>Here, with a median prison wage of 2.70 $/hour, incarcerated people in Nevada have to work about 0.37 hours for that same $1.00 worth of earnings.</p>",
    "<p></p>",
  ];

  // $: dollarSteps = [0, 1, 2, 3, 4, 5]
  // $: toothpasterSteps = [8, 1, 2, 3, 4, 5]

  // $: redSteps = [0, 1, 2,7]
  // $: blueSteps = [3,8]
  // $: yellowSteps = [4,5,6,9]

  // penny stacks 6,
  // penny stacks highlighted NV 7
  // penny stacks highlighted NV alone

  // $: color = redSteps.includes(value)?"red":blueSteps.includes(value)?"blue":yellowSteps.includes(value)?"yellow":"purple"
  $: blur = [0];
  $: pennyStacks = [];
  $: pennyStacksNV = [1];
  $: pennyStacksNV_gap = [2];
  $: pennyStacksWS_stateMin = [3];
  $: pennyStacksWS_gap = [4];
  $: laborPerDollar = [5];
  $: center = [];
  $: blank = [];

  $: svgName = blur.includes(value)
    ? "MedianWage_blur_app"
    : blank.includes(value)
    ? "Blank_app"
    : pennyStacks.includes(value)
    ? "MedianWage_app"
    : pennyStacksNV.includes(value)
    ? "MedianWageNV_highlight_app"
    : pennyStacksNV_gap.includes(value)
    ? "MedianWageNV_gap_app"
    : pennyStacksWS_stateMin.includes(value)
    ? "MedianWageWS_stateMin_app"
    : pennyStacksWS_gap.includes(value)
    ? "MedianWage_WS_gap"
    : laborPerDollar.includes(value)
    ? "LaborPerDollar_app"
    : "MedianWage_blur_app";

  $: align = center.includes(value) ? "center" : "left";

  $: console.log("current step: ", value);

  $: laptop = innerWidth > 800;

  // $: imgWidth = innerWidth>1200?innerWidth * 0.6:innerWidth * 0.7;
  // $: imgHeight = innerHeight * 0.9;
  $: imgWidth = 800;
  $: imgHeight = 800;

  $: innerWidth = 0;
  $: innerHeight = 0;
  $: outerHeight = 0;
  $: outerWidth = 0;

  $: console.log("screenwidth", innerWidth);
</script>

<svelte:window
  bind:innerHeight
  bind:innerWidth
  bind:outerHeight
  bind:outerWidth
/>
<main>
  <!-- <div>
    <a href="https://vitejs.dev" target="_blank" rel="noreferrer"> 
      <img src="/vite.svg" class="logo" alt="Vite Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank" rel="noreferrer"> 
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>
  <h1>Vite + Svelte</h1>

  <div class="card">
    <Counter />
  </div>
  <div class="card">
    <button on:click={()=>{
      // shapeShift('circles')
      shape='circles'
      }}>
      Circles
    </button>

    <button on:click={()=>{
    // shapeShift('rectangles')
    shape='rectangles'
    }}>
      Rectangles
    </button>

    {#if shape==='circles'}
      <Circles />
    {:else}
      <Rectangles/>     
    {/if}
  </div>

  <p>
    Check out <a href="https://github.com/sveltejs/kit#readme" target="_blank" rel="noreferrer">SvelteKit</a>, the official Svelte app framework powered by Vite!
  </p>

  <p class="read-the-docs">
    Click on the Vite and Svelte logos to learn more
  </p> -->
  {#if laptop}
    <section>
      <Intro />
    </section>
    <section>
      <div class="hero" />
      <div class="section-container">
        <div class="steps-container">
          <Scrolly bind:value>
            {#each steps as text, i}
              <div class="step" class:active={value === i}>
                <div class="step-content" style="text-align: {align};">
                  {@html text}
                </div>
              </div>
            {/each}
            <div class="spacer" />
          </Scrolly>
        </div>
        <!-- {#if value!==undefined} -->
        <div class="sticky">
          <!-- <div class= "stickyContent" style="background-color: {color};">

          </div> -->
          <!-- <img href="./public/svg/{svgName}.svg" alt="Visualization related to what a dollar costs for folks incarcerated in the US" width="70%"> -->
          <svg width={imgWidth} height={imgHeight}>
            <image xlink:href="./svg/{svgName}.svg" width="100%" />
            <!-- <image xlink:href="./public/svg/{svgName}.svg" width="100%" /> -->
            {#if value === 1}
              <Arrow x1={80} x2={50} y1={100} y2={100} />
              {#each 'At 2.70 $/hour, Nevada//has the highest//median prison wage'.split('//') as substring, i}
                <text 
                class="annotation" 
                x="80" 
                y={100+i*14} 
                dx="10" 
                fill="b"
                  >{substring}
                </text>
              {/each}
            {/if}

            {#if value === 2}
            <Arrow x1={0} x2={0} y1={0} y2={0} />
            {#each 'Incarcerated workers// in Nevada earn// 7.8 $/hour less than// Nevada workers// who earn the state// mandated minimum //wage'.split('//') as substring, i}
              <text 
              class="annotation" 
              x="180" 
              y={185+i*14} 
              dx="10" 
              fill="b"
                >{substring}
              </text>
            {/each}
          {/if}

          {#if value === 4}
          <Arrow x1={580} x2={530} y1={510} y2={540} />
          {#each 'Incarcerated workers in //Arkansas, Georgia, and// Texas earn 0 $/hour'.split('//') as substring, i}
            <text 
            class="annotation" 
            x="520" 
            y={475+i*14} 
            dx="10" 
            fill="b"
              >{substring}
            </text>
          {/each}
        {/if}


          </svg>
        </div>
        <!-- {:else}
        <div class="sticky">
          
        </div>
      {/if} -->
      </div>
      <div class="hero">
        <h1>Thanks!</h1>
        <h2>
          <a href="https://twitter.com/CL_Rothschild" target="_blank"
            >Questions and Tips</a
          >
        </h2>
      </div>
    </section>
  {:else}
    <h2>
      This article has not been optimized for small screens, sorry! Please go
      into full-screen mode or use a larger device. Thank you!
    </h2>
  {/if}
</main>

<style>
  /* .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  } */

  :global(body) {
    overflow-x: hidden;
  }

  .hero {
    height: 60vh;
    display: flex;
    place-items: center;
    flex-direction: column;
    justify-content: center;
    text-align: center;
    /* font-family: Arial; */
  }

  .hero h2 {
    margin-top: 0;
    font-weight: 200;
  }

  .spacer {
    height: 40vh;
  }

  .sticky {
    position: sticky;
    top: 10%;
    flex: 1 1 60%;
    width: 100%;
    text-align: center;
    z-index: -100;
  }

  .section-container {
    margin-top: 1em;
    text-align: center;
    transition: background 100ms;
    display: flex;
  }

  .step {
    height: 90vh;
    display: flex;
    place-items: center;
    justify-content: center;
  }

  .step-content {
    font-size: 1rem;
    background: whitesmoke;
    color: #ccc;
    border-radius: 5px;
    padding: 0.5rem 1rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    transition: background 500ms ease;
    box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.2);

    width: 75%;
    margin: auto;
    max-width: 500px;
  }

  .step.active .step-content {
    background: white;
    color: black;
  }

  .section-container {
    flex-direction: column-reverse;
  }

  .stickyContent {
    width: 50%;
    height: 200px;
    margin: auto;
  }

  .annotation {
    font-size: 12px;
    margin: auto;
    font-family: 'Roboto Flex', sans-serif;
  }
</style>
