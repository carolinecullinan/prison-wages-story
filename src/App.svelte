<script>
  // @ts-ignore
  import svelteLogo from "./assets/svelte.svg";
  import Counter from "./lib/Counter.svelte";
  import Circles from "./lib/Circles.svelte";
  import Rectangles from "./lib/Rectangles.svelte";
  import Scrolly from "./lib/Scrolly.svelte";
  import Intro from "./lib/Intro.svelte";
  import Arrow from "./lib/Arrow.svelte";

  import laborPerDollarUrl from "./svg/LaborPerDollar_app.png";
  import phoneIconUrl from "./svg/phoneIcon_app.png";
  import toothpasteIconUrl from "./svg/toothpasteIcon_app.png";
  import riceIconUrl from "./svg/riceIcon_app.png";
  import penIconUrl from "./svg/penIcon_app.png";

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
    "<p>Given this information, we can try to understand what a dollar costs in the US prison system in terms of <span style = 'color: #7695c4; font-weight: 700'>labor</span>. In each state, how many hours of <span style = 'color: #7695c4; font-weight: 700'>labor</span> equate to <span style = 'color: #7695c4; font-weight: 700'>$1.00</span> in prison wages? <br></br> Given the fact that people in <span style = 'color: #ff9f3f; font-weight: 700'>Arkansas</span>, <span style = 'color: #ff9f3f; font-weight: 700'>Georgia</span>, and <span style = 'color: #ff9f3f; font-weight: 700'>Texas</span> aren’t financially compensated at all for their prison labor, folks incarcerated in these states can’t even earn a dollar. Essentially, people in these states have to work for free. However in considering other states, and in terms of <span style = 'color: #7695c4; font-weight: 700'>labor</span> conducted, we can see that a dollar costs the most in <span style = 'color: #ff9f3f; font-weight: 700'>Alabama</span>.</p>",
    "<p>With a median prison wage of <span style = 'color: #7695c4; font-weight: 700'>0.12 $/hour</span>, incarcerated people in <span style = 'color: #ff9f3f; font-weight: 700'>Alabama</span> must conduct <span style = 'color: #7695c4; font-weight: 700'>8.33 hours</span> of labor at the median prison wage in order to earn a single dollar.<br></br> On the other hand, this same $1.00 is least expensive in the state of <span style = 'color: #ff9f3f; font-weight: 700'>Nevada</span>. Here, with a median prison wage of <span style = 'color: #7695c4; font-weight: 700'>2.70 $/hour</span>, incarcerated people in <span style = 'color: #ff9f3f; font-weight: 700'>Nevada</span> have to work about <span style = 'color: #7695c4; font-weight: 700'>0.37 hours</span> for that same $1.00 worth of earnings.</p>",
    "<p>At a glance it may appear as if incarcerated people in <span style = 'color: #ff9f3f; font-weight: 700'>Nevada</span> are subjected to fairer prison wages. However, for that same $1.00 worth of earnings, these workers have to work about <span style = 'color: #7695c4; font-weight: 700'>16 and a half minutes longer</span> than non-incarcerated <span style = 'color: #ff9f3f; font-weight: 700'>Nevada</span> workers who earn the government mandated minimum wage.<br></br> In other terms, this means that in <span style = 'color: #ff9f3f; font-weight: 700'>Nevada</span>, incarcerated folks have to work <span style = 'color: #7695c4; font-weight: 700'>289% more</span> for that same $1.00 than non-incarcerated folks.</p>",
    "<p>And what can these hard-worked hours buy? Phone calls with loved ones, hygiene products, food, and miscellaneous items like writing utensils can all be purchased from prison.<br></br>To get an idea of the amount of <span style = 'color: #7695c4; font-weight: 700'>labor</span> that incarcerated folks need to perform in different states in order to be able to afford items that help them meet some of their basic needs, this quick-dive considers the average cost of: a <span style = 'color: #7695c4; font-weight: 700'>15-minute </span> (in-state) <span style = 'color: #7695c4; font-weight: 700'>phone call </span>, a tube of <span style = 'color: #7695c4; font-weight: 700'>toothpaste</span>, a pack of <span style = 'color: #7695c4; font-weight: 700'>rice</span>, and an ink <span style = 'color: #7695c4; font-weight: 700'>pen</span>.</p>",
    "<p>Given the median prison wage and the average cost of prison phone time across states, the hours of labor that incarcerated workers must perform for a <span style = 'color: #7695c4; font-weight: 700'>15-minute phone call</span> with loved ones on the outside was calculated.</p>",
    "<p>While incarcerated people in <span style = 'color: #ff9f3f; font-weight: 700'>Connecticut</span> and <span style = 'color: #ff9f3f; font-weight: 700'>California</span> can freely call loved ones without any charge for the minutes spent on the phone, folks incarcerated in other states aren’t as fortunate.<br></br> Considering states where incarcerated people are compensated at all for their labor, folks incarcerated in <span style = 'color: #ff9f3f; font-weight: 700'>Pennsylvania</span> are worst off. Here, incarcerated people have to work about <span style = 'color: #7695c4; font-weight: 700'>29 and half hours</span> at the median prison wage just to be able to afford 15 minutes of phone time.<br></br>And remember <span style = 'color: #ff9f3f; font-weight: 700'>Arkansas</span>, <span style = 'color: #ff9f3f; font-weight: 700'>Georgia</span>, and <span style = 'color: #ff9f3f; font-weight: 700'>Texas</span>? In these states, incarcerated people work for free, which means that they can’t even buy their own phone time.</p>",
    "<p>And hygiene? Surely incarcerated people shouldn’t be subjected to hard-labor just to be able to afford something as essential to personal hygiene as a tube of <span style = 'color: #7695c4; font-weight: 700'>toothpaste</span>, right?</p>",
    "<p>While incarcerated people earning the median prison wage in <span style = 'color: #ff9f3f; font-weight: 700'>Maine</span> may “only” need to work roughly <span style = 'color: #7695c4; font-weight: 700'>2 hours and 15 minutes</span> to be able to afford a typical tube of toothpaste from their prison canteen, those incarcerated in <span style = 'color: #ff9f3f; font-weight: 700'>Alabama</span> prisons have to work a staggering <span style = 'color: #7695c4; font-weight: 700'>33 hours</span> at the median prison wage for that same tube of toothpaste. This basically means that in <span style = 'color: #ff9f3f; font-weight: 700'>Alabama</span>, incarcerated folks have to put in more than <span style = 'color: #7695c4; font-weight: 700'>4 full 8-hour work days </span> before they can afford to keep their teeth clean. </p>",
    "<p>And when it comes to food, incarcerated people looking to supplement their prison cafeteria diet with additional food items can also do so at a laborious cost. Let's consider a typical pack of <span style = 'color: #7695c4; font-weight: 700'>rice</span>, for example.<br></br>While not every state prison commissary sampled made <span style = 'color: #7695c4; font-weight: 700'>rice</span> available for purchase (e.g., <span style = 'color: grey; font-weight: 700'>Maine</span> and <span style = 'color: grey; font-weight: 700'>Montana</span>), incarcerated folks across the US had more or less general access to this food item. However, prices for commissary prison <span style = 'color: #7695c4; font-weight: 700'>rice</span> varied widely across states.</p>",
    "<p>Once again, incarcerated folks in <span style = 'color: #ff9f3f; font-weight: 700'>Alabama</span> had to work the most at the median prison wage to be able to afford this product. A typical pack of rice for people incarcerated in this state costs about <span style = 'color: #7695c4; font-weight: 700'>11 hours and 40 minutes</span> of labor.<br></br>Contrastingly, with about <span style = 'color: #7695c4; font-weight: 700'>an hour</span> of work at the median prison wage, folks incarcerated in <span style = 'color: #ff9f3f; font-weight: 700'>New Jersey</span> can purchase this same pack of rice.</p>",
    "<p>And finally: the ink <span style = 'color: #7695c4; font-weight: 700'>pen</span>. Crucial for writing, learning, and communicating with others,  the <span style = 'color: #7695c4; font-weight: 700'>pen</span> is an indispensable tool for day-to-day life both inside and outside of prison. So as valuable as this miscellaneous item is, what’s it cost for those incarcerated?</p>",
    "<p>Not every state prison commissary sampled made ink <span style = 'color: #7695c4; font-weight: 700'>pens</span> available for purchase (e.g., <span style = 'color: grey; font-weight: 700'>Montana</span>, <span style = 'color: grey; font-weight: 700'>Nebraska</span>, and <span style = 'color: grey; font-weight: 700'>Utah</span>).<br></br>However with these pen-less states and <span style = 'color: #ff9f3f; font-weight: 700'>Arkansas</span>, <span style = 'color: #ff9f3f; font-weight: 700'>Georgia</span>, and <span style = 'color: #ff9f3f; font-weight: 700'>Texas</span> aside (i.e., states where incarcerated folks aren’t paid for their labor), the hours of work that incarcerated people have to perform at the median prison wage to be able to afford the average prison commissary ink <span style = 'color: #7695c4; font-weight: 700'>pen</span> was calculated across the US.<br></br>While incarcerated folks in <span style = 'color: #ff9f3f; font-weight: 700'>Minnesota</span> may have to put in only <span style = 'color: #7695c4; font-weight: 700'>12 minutes</span> of labor to be able to purchase an ink pen, folks incarcerated in <span style = 'color: #ff9f3f; font-weight: 700'>Oklahoma</span> have to put in more than <span style = 'color: #7695c4; font-weight: 700'>16 hours</span> of work for that same pen. And this basically means that the difference between being incarcerated in <span style = 'color: #ff9f3f; font-weight: 700'>Oklahoma</span> instead of <span style = 'color: #ff9f3f; font-weight: 700'>Minnesota</span> is more than <span style = 'color: #7695c4; font-weight: 700'>8030%</span> more labor just to be able to write a letter home to your loved ones.</p>",
    "<p></p>",
    "<p></p>",
    "<p></p>",
    "<p></p>",
    "<p></p>",
    "<p></p>",
    "<p></p>",
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
  $: laborPerDollar = [5, 6, 7];
  $: phoneIcon = [9];
  $: laborPerPhone15 = [10];
  $: toothpasteIcon = [11];
  $: laborPerToothpaste = [12];
  $: riceIcon = [13];
  $: laborPerRice = [14];
  $: penIcon = [15];
  $: LaborPerPen = [16];
  $: center = [];
  $: blank = [8, 17];

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
    : laborPerPhone15.includes(value)
    ? "LaborPerPhone15_app"
    : laborPerToothpaste.includes(value)
    ? "LaborPerToothpaste_app"
    : laborPerRice.includes(value)
    ? "LaborPerRice_app"
    : LaborPerPen.includes(value)
    ? "LaborPerPen_app"
    : laborPerDollar.includes(value)
    ? laborPerDollarUrl
    : phoneIcon.includes(value)
    ? phoneIconUrl
    : toothpasteIcon.includes(value)
    ? toothpasteIconUrl
    : riceIcon.includes(value)
    ? riceIconUrl
    : penIcon.includes(value)
    ? penIconUrl
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
            {#if !laborPerDollar.includes(value)}
              <image xlink:href="./svg/{svgName}.svg" width="100%" />
            {:else}
              <image
                xlink:href={svgName}
                width="90%"
                style="transform:translate(80px, -50px)"
              />
            {/if}

            <svg width={imgWidth} height={imgHeight}>
              {#if !phoneIcon.includes(value)}
                <image xlink:href="./svg/{svgName}.svg" width="100%" />
              {:else}
                <image
                  xlink:href={svgName}
                  width="90%"
                  style="transform:translate(60px, 230px)"
                />
              {/if}

              <svg width={imgWidth} height={imgHeight}>
                {#if !toothpasteIcon.includes(value)}
                  <image xlink:href="./svg/{svgName}.svg" width="100%" />
                {:else}
                  <image
                    xlink:href={svgName}
                    width="90%"
                    style="transform:translate(60px, 230px)"
                  />
                {/if}

                <svg width={imgWidth} height={imgHeight}>
                  {#if !riceIcon.includes(value)}
                    <image xlink:href="./svg/{svgName}.svg" width="100%" />
                  {:else}
                    <image
                      xlink:href={svgName}
                      width="90%"
                      style="transform:translate(60px, 230px)"
                    />
                  {/if}

                  <svg width={imgWidth} height={imgHeight}>
                    {#if !penIcon.includes(value)}
                      <image xlink:href="./svg/{svgName}.svg" width="100%" />
                    {:else}
                      <image
                        xlink:href={svgName}
                        width="90%"
                        style="transform:translate(60px, 230px)"
                      />
                    {/if}
                    <!-- <image xlink:href="./public/svg/{svgName}.svg" width="100%" /> -->
                    {#if value === 1}
                      <Arrow x1={80} x2={50} y1={100} y2={100} />
                      {#each "At 2.70 $/hour, Nevada//has the highest//median prison wage".split("//") as substring, i}
                        <text
                          class="annotation"
                          x="80"
                          y={100 + i * 14}
                          dx="10"
                          fill="b"
                          >{substring}
                        </text>
                      {/each}
                    {/if}

                    {#if value === 2}
                      <Arrow x1={0} x2={0} y1={0} y2={0} />
                      {#each "Incarcerated workers// in Nevada earn// 7.8 $/hour less than// Nevada workers// who earn the state// mandated minimum //wage".split("//") as substring, i}
                        <text
                          class="annotation"
                          x="215"
                          y={215 + i * 14}
                          dx="10"
                          fill="b"
                          >{substring}
                        </text>
                      {/each}
                    {/if}

                    {#if value === 4}
                      <Arrow x1={670} x2={600} y1={590} y2={610} />
                      {#each "Incarcerated workers in //Arkansas, Georgia, and// Texas earn 0 $/hour".split("//") as substring, i}
                        <text
                          class="annotation"
                          x="600"
                          y={555 + i * 14}
                          dx="10"
                          fill="b"
                          >{substring}
                        </text>
                      {/each}
                    {/if}

                    {#if value === 5}
                      <Arrow x1={730} x2={750} y1={530} y2={620} />
                      {#each "People in Arkansas,// Georgia, and Texas// aren’t financially// compensated at all// for their prison labor, // therefore folks //incarcerated in// these states can’t// even earn a//dollar. ".split("//") as substring, i}
                        <text
                          class="annotation"
                          x="675"
                          y={400 + i * 14}
                          dx="10"
                          fill="b"
                          >{substring}
                        </text>
                      {/each}
                    {/if}

                    {#if value === 6}
                      <Arrow x1={730} x2={720} y1={570} y2={600} />
                      {#each "In Alabama, incarcerated// people have to work,// on average, 8 hours// and 20 miuntes for// a dollar of earnings".split("//") as substring, i}
                        <text
                          class="annotation"
                          x="650"
                          y={500 + i * 14}
                          dx="10"
                          fill="b"
                          >{substring}
                        </text>
                      {/each}

                      <Arrow x1={240} x2={210} y1={50} y2={60} />
                      {#each "On average, incarcerated// people in Nevada have// to work about 22 minutes// to earn a single dollar".split("//") as substring, i}
                        <text
                          class="annotation"
                          x="245"
                          y={50 + i * 14}
                          dx="10"
                          fill="b"
                          >{substring}
                        </text>
                      {/each}
                    {/if}

                    {#if value === 7}
                      <Arrow x1={240} x2={210} y1={50} y2={60} />
                      {#each "On average, incarcerated// people in Nevada have// to work about 22 minutes// to earn a single dollar".split("//") as substring, i}
                        <text
                          class="annotation"
                          x="245"
                          y={50 + i * 14}
                          dx="10"
                          fill="b"
                          >{substring}
                        </text>
                      {/each}
                    {/if}
                  </svg>
                </svg></svg
              ></svg
            ></svg
          >
        </div>
        <!-- {:else}
        <div class="sticky">
          
        </div>
      {/if} -->
      </div>
      <!-- <div class="hero">
        <h1>Thanks!</h1>
        <h2>
          <a href="https://twitter.com/CL_Rothschild" target="_blank"
            >Questions and Tips</a
          >
        </h2>
      </div> -->
    </section>
  {:else}
    <h2>
      This article has not been optimized for small screens, sorry! Please use
      full-screen mode or use a larger device. Thank you!
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
    font-family: "Roboto Flex", sans-serif;
  }
</style>
