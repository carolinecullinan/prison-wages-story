<script>
  // @ts-ignore
  import svelteLogo from "./assets/svelte.svg";
  import Counter from "./lib/Counter.svelte";
  import Circles from "./lib/Circles.svelte";
  import Rectangles from "./lib/Rectangles.svelte";
  import Scrolly from "./lib/Scrolly.svelte";
  import Intro from "./lib/Intro.svelte";
  import Outro from "./lib/Outro.svelte";
  import Arrow from "./lib/Arrow.svelte";

  import laborPerDollarUrl from "./svg/LaborPerDollar_app.png";
  import phoneIconUrl from "./svg/phoneIcon_app.png";
  import toothpasteIconUrl from "./svg/toothpasteIcon_app.png";
  import riceIconUrl from "./svg/riceIcon_app.png";
  import penIconUrl from "./svg/penIcon_app.png";
  import blurUrl from "./svg/MedianWage_blur_app.png";
  import pennyStacksUrl from "./svg/MedianWage_app.png";
  import laborPerDollarBlurUrl from "./svg/LaborPerDollar_blur_app.png";
  import MedianWageWS_stateMin_appUrl from "./svg/MedianWageWS_stateMin_app.png";
  import MedianWageWS_gap_appUrl from "./svg/MedianWage_WS_gap_app.png";
  import MedianWageNV_gap_appUrl from "./svg/MedianWageNV_gap_app.png";
  import LaborPerPhone15_appUrl from "./svg/LaborPerPhone15_app.png";
  import LaborPerToothpaste_appUrl from "./svg/LaborPerToothpaste_app.png";
  import LaborPerRice_appUrl from "./svg/LaborPerRice_app.png";
  import LaborPerPen_appUrl from "./svg/LaborPerPen_app.png";
  import Blank_appUrl from "./svg/Blank_app.png";





  // let shape = 'circles'

  // const shapeShift=(s)=>{
  //   shape = s
  //   console.log(shape)
  // }

  let value = 0;
  const steps = [
    "<p>Firstly, before we can quantify the cost of a dollar in US prisons, we need to understand wages earned by incarcerated people in the US. Different prison jobs are compensated at various rates across US states. Regardless, we can use a <span style = 'color: #7695c4; font-weight: 600'>median wage</span> for prison labor as a <span style = 'color: #ff9f3f; font-weight: 600'>state-based</span> metric for this analysis.</p>",
    "<p>Here, for example, we can see that the state of <span style = 'color: #ff9f3f; font-weight: 600'>Nevada</span> has the highest median prison wage.</p>",
    "<p>But regardless of the fact that <span style = 'color: #ff9f3f; font-weight: 600'>Nevada</span> ranks highest in median prison wages when compared to all other US states, incarcerated workers in Nevada are still inadequately compensated.   When considering the median prison wage, incarcerated people in Nevada earn only <span style = 'color: #7695c4; font-weight: 600'>26%</span> of the government mandated minimum wage.</p>",
    "<p>Alternatively, the government mandated minimum wages in <span style = 'color: #ff9f3f; font-weight: 600'>Arkansas</span>, <span style = 'color: #ff9f3f; font-weight: 600'>Georgia</span>, and <span style = 'color: #ff9f3f; font-weight: 600'>Texas</span> are <span style = 'color: #7695c4; font-weight: 600'>11.00 $/hour</span>, <span style = 'color: #7695c4; font-weight: 600'>7.25 $/hour</span>, and <span style = 'color: #7695c4; font-weight: 600'>7.25 $/hour</span> respectively.</p>",
    "<p>However, these states don???t compensate incarcerated workers at all for their labor.  Folks incarcerated in <span style = 'color: #ff9f3f; font-weight: 600'>Arkansas</span>, <span style = 'color: #ff9f3f; font-weight: 600'>Georgia</span>, and <span style = 'color: #ff9f3f; font-weight: 600'>Texas</span> must work for free, which means that they earn <span style = 'color: #7695c4; font-weight: 600'>100% less</span> than non-incarcerated people who earn the government mandated minimum wage in each respective state.</p>",
    "<p>Now, with this information, we can try to understand what a dollar costs in the US prison system in terms of <span style = 'color: #7695c4; font-weight: 600'>labor</span>. In each state, how many hours of labor equate to $1.00 in prison wages? </p>",
    "<p> Given the fact that people in <span style = 'color: #ff9f3f; font-weight: 600'>Arkansas</span>, <span style = 'color: #ff9f3f; font-weight: 600'>Georgia</span>, and <span style = 'color: #ff9f3f; font-weight: 600'>Texas</span> aren???t financially compensated at all for their prison labor, folks incarcerated in these states can???t even earn a dollar.  These people have to work for free.</p>",
    "<p>However, in considering states that provide some financial compensation for prison labor, we can see that a dollar costs the most in <span style = 'color: #ff9f3f; font-weight: 600'>Alabama</span>. With a median prison wage of 0.12 $/hour, incarcerated people in Alabama must conduct <span style = 'color: #7695c4; font-weight: 600'>8.33 hours</span> of labor at the median prison wage in order to earn a single dollar.</p>",
    "<p>On the other hand, this same $1.00 is least expensive in the state of <span style = 'color: #ff9f3f; font-weight: 600'>Nevada</span>. Here, with a median prison wage of 2.70 $/hour, incarcerated people in Nevada have to work about <span style = 'color: #7695c4; font-weight: 600'>0.37 hours</span> for that same $1.00 worth of earnings.<br><br>At a glance, it may appear as if incarcerated people in Nevada are subjected to fairer prison wages when compared to other US states. However, for that same $1.00 worth of earnings, these workers have to work about <span style = 'color: #7695c4; font-weight: 600'>16 and a half minutes longer</span> than non-incarcerated Nevada workers who earn the government mandated minimum wage. In other terms, this means that in Nevada, incarcerated folks have to work <span style = 'color: #7695c4; font-weight: 600'>289% more</span> for that same $1.00 than non-incarcerated folks.</p>",
    "<div style='text-align:center;width:100%;font-size:50px'>.  .  .</div><br><p>So, now that we understand the cost of a dollar in terms of US prison labor, let's try to understand the purchasing power of such prison labor. What can these hard-worked hours buy? To get a better idea about the amount of labor that incarcerated folks need to perform in different US states in order to be able to afford different items that help them meet some of their basic needs, this quick-dive considers the average cost of a <span style = 'color: #7695c4; font-weight: 600'>15-minute </span> (in-state) <span style = 'color: #7695c4; font-weight: 600'>phone call </span>, a tube of <span style = 'color: #7695c4; font-weight: 600'>toothpaste</span>, a pack of <span style = 'color: #7695c4; font-weight: 600'>rice</span>, and an ink <span style = 'color: #7695c4; font-weight: 600'>pen</span>.</p>",
    "<p>Given the median prison wage and the average cost of prison phone time across states, the hours of labor that incarcerated workers must perform for a <span style = 'color: #7695c4; font-weight: 600'>15-minute phone call</span> with loved ones on the outside was calculated.</p>",
    "<p>While incarcerated people in <span style = 'color: #ff9f3f; font-weight: 600'>Connecticut</span> and <span style = 'color: #ff9f3f; font-weight: 600'>California</span> can freely call loved ones without any charge for the minutes spent on the phone, folks incarcerated in other states aren???t as fortunate. In <span style = 'color: #ff9f3f; font-weight: 600'>Arkansas</span>, <span style = 'color: #ff9f3f; font-weight: 600'>Georgia</span>, and <span style = 'color: #ff9f3f; font-weight: 600'>Texas</span>, where prison labor is conducted for free, incarcerated people can't even buy their own phone time with an earned wage. But in only considering states where incarcerated people are financially compensated for their labor, we can see that those incarcerated in <span style = 'color: #ff9f3f; font-weight: 600'>Pennsylvania</span> are worst off. Here, incarcerated people have to work about <span style = 'color: #7695c4; font-weight: 600'>29 and half hours</span> at the median prison wage just to be able to afford 15 minutes of phone time.<br><br></p>",
    "<p>And hygiene? Surely incarcerated people shouldn???t be subjected to hard-labor just to be able to afford something as essential to personal hygiene as a tube of <span style = 'color: #7695c4; font-weight: 600'>toothpaste</span>, right?</p>",
    "<p>While incarcerated people earning the median prison wage in <span style = 'color: #ff9f3f; font-weight: 600'>Maine</span> may ???only??? need to work roughly <span style = 'color: #7695c4; font-weight: 600'>2 hours and 15 minutes</span> to be able to afford a typical tube of toothpaste from their prison canteen, those incarcerated in <span style = 'color: #ff9f3f; font-weight: 600'>Alabama</span> prisons have to work a staggering <span style = 'color: #7695c4; font-weight: 600'>33 hours</span> at the median prison wage for that same tube of toothpaste. This basically means that in Alabama, incarcerated folks have to put in more than <span style = 'color: #7695c4; font-weight: 600'>4 full 8-hour work days </span> before they can afford to keep their teeth clean. </p>",
    "<p>And when it comes to food, incarcerated people looking to supplement their prison cafeteria diet with additional food items can also do so at a laborious cost. Let's consider a typical pack of <span style = 'color: #7695c4; font-weight: 600'>rice</span>, for example.<br><br>While not every state prison commissary sampled made rice  available for purchase (e.g., <span style = 'color: grey; font-weight: 600'>Maine</span> and <span style = 'color: grey; font-weight: 600'>Montana</span>), incarcerated folks across the US seem to have more or less general access to this food item. However, prices for commissary prison rice also appear to vary widely across states.</p>",
    "<p>Once again, incarcerated folks in <span style = 'color: #ff9f3f; font-weight: 600'>Alabama</span> have to work the most at the median prison wage to be able to afford this product. A typical pack of rice for people incarcerated in this state costs about <span style = 'color: #7695c4; font-weight: 600'>11 hours and 40 minutes</span> of labor. Contrastingly, with about <span style = 'color: #7695c4; font-weight: 600'>an hour</span> of labor at the median prison wage, folks incarcerated in <span style = 'color: #ff9f3f; font-weight: 600'>New Jersey</span> can purchase this same pack of rice.</p>",
    "<p>And finally, the ink <span style = 'color: #7695c4; font-weight: 600'>pen</span>. Crucial for learning, self-expression, and communicating with others,  the pen is an indispensable tool for day-to-day life both inside and outside of prison. So as valuable as this miscellaneous item is, what???s it cost for those incarcerated?</p>",
    "<p>Unfortunately, not every state prison commissary sampled made ink pens available for purchase (e.g., <span style = 'color: grey; font-weight: 600'>Montana</span>, <span style = 'color: grey; font-weight: 600'>Nebraska</span>, and <span style = 'color: grey; font-weight: 600'>Utah</span>). However with these pen-less states and <span style = 'color: #ff9f3f; font-weight: 600'>Arkansas</span>, <span style = 'color: #ff9f3f; font-weight: 600'>Georgia</span>, and <span style = 'color: #ff9f3f; font-weight: 600'>Texas</span> aside (i.e., states where incarcerated folks aren???t paid for their labor), the hours of work that incarcerated people have to perform at the median prison wage to be able to afford the average prison commissary ink pen was calculated across the US.<br><br>While incarcerated folks in <span style = 'color: #ff9f3f; font-weight: 600'>Minnesota</span> may have to put in only <span style = 'color: #7695c4; font-weight: 600'>12 minutes</span> of labor to be able to purchase an ink pen, folks incarcerated in <span style = 'color: #ff9f3f; font-weight: 600'>Oklahoma</span> have to put in more than <span style = 'color: #7695c4; font-weight: 600'>16 hours</span> of work for that same writing utensil. And this basically means that the difference between being incarcerated in Oklahoma instead of Minnesota is more than <span style = 'color: #7695c4; font-weight: 600'>8030%</span> more labor just to be able to write a letter home to your loved ones.</p>",
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
  $: pennyStacks = [1];
  $: pennyStacksNV_gap = [2];
  $: pennyStacksWS_stateMin = [3];
  $: pennyStacksWS_gap = [4];
  $: laborPerDollarBlur = [5];
  $: laborPerDollar = [6, 7, 8];
  $: phoneIcon = [10];
  $: laborPerPhone15 = [11];
  $: toothpasteIcon = [12];
  $: laborPerToothpaste = [13];
  $: riceIcon = [14];
  $: laborPerRice = [15];
  $: penIcon = [16];
  $: LaborPerPen = [17];
  $: dollarPusher = [19];
  $: center = [];
  $: blank = [9, 18];

  $: svgName = blur.includes(value)
    ? blurUrl
    : blank.includes(value)
    ? Blank_appUrl
    : pennyStacks.includes(value)
    ? pennyStacksUrl
    : pennyStacksNV_gap.includes(value)
    ? MedianWageNV_gap_appUrl
    : pennyStacksWS_stateMin.includes(value)
    ? MedianWageWS_stateMin_appUrl
    : pennyStacksWS_gap.includes(value)
    ? MedianWageWS_gap_appUrl
    : laborPerDollarBlur.includes(value)
    ? laborPerDollarBlurUrl
    : laborPerPhone15.includes(value)
    ? LaborPerPhone15_appUrl
    : laborPerToothpaste.includes(value)
    ? LaborPerToothpaste_appUrl
    : laborPerRice.includes(value)
    ? LaborPerRice_appUrl
    : LaborPerPen.includes(value)
    ? LaborPerPen_appUrl 
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
    : "Blank_app";

  $: transform = `transform:translate(${imgWidth/2-(imgWidth*0.9)/2}px, ${(innerHeight-(imgHeight*0.9))/2}px)`

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
            <g>
            {#if !blur.includes(value)}
              <image xlink:href="./svg/{svgName}.svg" width="100%" />
            {:else}
              <image
                xlink:href={svgName}
                width="90%"
                style="transform:translate({imgWidth/2-(imgWidth*0.9)/2}px, {(innerHeight-(imgHeight*0.9))/2}px)"
              />
            {/if}

            {#if !pennyStacks.includes(value)}
              <image xlink:href="./svg/{svgName}.svg" width="100%" />
            {:else}
              <image
                xlink:href={svgName}
                width="90%"
                style="transform:translate({imgWidth/2-(imgWidth*0.9)/2}px, {(innerHeight-(imgHeight*0.9))/2}px)"
              />
            {/if}

            <!-- <svg width={imgWidth} height={imgHeight}> -->
            {#if !pennyStacksNV_gap.includes(value)}
              <image xlink:href="./svg/{svgName}.svg" width="100%" />
            {:else}
              <image
                xlink:href={svgName}
                width="90%"
                style="transform:translate({imgWidth/2-(imgWidth*0.9)/2}px, {(innerHeight-(imgHeight*0.9))/2}px)"
              />
            {/if}

            <!-- <svg width={imgWidth} height={imgHeight}> -->
            {#if !pennyStacksWS_stateMin.includes(value)}
              <image xlink:href="./svg/{svgName}.svg" width="100%" />
            {:else}
              <image
                xlink:href={svgName}
                width="90%"
                style="transform:translate({imgWidth/2-(imgWidth*0.9)/2}px, {(innerHeight-(imgHeight*0.9))/2}px)"
              />
            {/if}

            <!-- <svg width={imgWidth} height={imgHeight}> -->
            {#if !pennyStacksWS_gap.includes(value)}
              <image xlink:href="./svg/{svgName}.svg" width="100%" />
            {:else}
              <image
                xlink:href={svgName}
                width="90%"
                style="transform:translate({imgWidth/2-(imgWidth*0.9)/2}px, {(innerHeight-(imgHeight*0.9))/2}px)"
              />
            {/if}

            <!-- <svg width={imgWidth} height={imgHeight}> -->
            {#if !laborPerDollarBlur.includes(value)}
              <image xlink:href="./svg/{svgName}.svg" width="100%" />
            {:else}
              <image
                xlink:href={svgName}
                width="90%"
                style="transform:translate({imgWidth/2-(imgWidth*0.9)/2}px, {(innerHeight-(imgHeight*1.2))/2}px)"
              />
            {/if}

            <!-- <svg width={imgWidth} height={imgHeight}> -->
            {#if !laborPerDollar.includes(value)}
              <image xlink:href="./svg/{svgName}.svg" width="100%" />
            {:else}
              <image
                xlink:href={svgName}
                width="90%"
                style="transform:translate({imgWidth/2-(imgWidth*0.9)/2}px, {(innerHeight-(imgHeight*1.2))/2})"
              />
            {/if}

                       <!-- <svg width={imgWidth} height={imgHeight}> -->
            {#if !blank.includes(value)}
              <image xlink:href="./svg/{svgName}.svg" width="100%" />
            {:else}
              <image
                xlink:href={svgName}
                width="90%"
                style="transform:translate({imgWidth/2-(imgWidth*0.9)/2}px, {(innerHeight-(imgHeight*1.2))/2})"
              />
            {/if}

            <!-- style="transform:translate(80px, -140px)" -->


            <!-- <svg width={imgWidth} height={imgHeight}> -->
            {#if !phoneIcon.includes(value)}
              <image xlink:href="./svg/{svgName}.svg" width="100%" />
            {:else}
              <image
                xlink:href={svgName}
                width="90%"
                style="transform:translate({imgWidth/2-(imgWidth*0.9)/2}px, {(innerHeight/2)-(imgHeight/2)/2}px)"
              />
            {/if}

            {#if !laborPerPhone15.includes(value)}
            <image xlink:href="./svg/{svgName}.svg" width="100%" />
          {:else}
            <image
              xlink:href={svgName}
              width="100%"
              style="transform:translate({imgWidth/2-(imgWidth*1)/2}px, {(innerHeight-(imgHeight*1))/2}px)"
            />
          {/if}

            <!-- <svg width={imgWidth} height={imgHeight}> -->
            {#if !toothpasteIcon.includes(value)}
              <image xlink:href="./svg/{svgName}.svg" width="100%" />
            {:else}
              <image
                xlink:href={svgName}
                width="90%"
                style="transform:translate({imgWidth/2-(imgWidth*0.9)/2}px, {(innerHeight/2)-(imgHeight/2)/2}px)"
              />
            {/if}

            {#if !laborPerToothpaste.includes(value)}
            <image xlink:href="./svg/{svgName}.svg" width="100%" />
          {:else}
            <image
              xlink:href={svgName}
              width="100%"
              style="transform:translate({imgWidth/2-(imgWidth*1)/2}px, {(innerHeight-(imgHeight*1))/2}px)"
            />
          {/if}

            <!-- <svg width={imgWidth} height={imgHeight}> -->
            {#if !riceIcon.includes(value)}
              <image xlink:href="./svg/{svgName}.svg" width="100%" />
            {:else}
              <image
                xlink:href={svgName}
                width="90%"
                style="transform:translate({imgWidth/2-(imgWidth*0.9)/2}px, {(innerHeight/2)-(imgHeight/2)/2}px)"
              />
            {/if}

            {#if !laborPerRice.includes(value)}
            <image xlink:href="./svg/{svgName}.svg" width="100%" />
          {:else}
            <image
              xlink:href={svgName}
              width="90%"
              style="transform:translate({imgWidth/2-(imgWidth*1)/2}px, {(innerHeight-(imgHeight*1))/2}px)"
            />
          {/if}

            <!-- <svg width={imgWidth} height={imgHeight}> -->
            {#if !penIcon.includes(value)}
              <image xlink:href="./svg/{svgName}.svg" width="100%" />
            {:else}
              <image
                xlink:href={svgName}
                width="90%"
                style="transform:translate({imgWidth/2-(imgWidth*0.9)/2}px, {(innerHeight/2)-(imgHeight/2)/2}px)"
              />
            {/if}

            
            {#if !LaborPerPen.includes(value)}
            <image xlink:href="./svg/{svgName}.svg" width="100%" />
          {:else}
            <image
              xlink:href={svgName}
              width="90%"
              style="transform:translate({imgWidth/2-(imgWidth*1)/2}px, {(innerHeight-(imgHeight*1))/2}px)"
            />
          {/if}

            <!-- <svg width={imgWidth} height={imgHeight}> -->
            {#if !dollarPusher.includes(value)}
              <image xlink:href="./svg/{svgName}.svg" width="100%" />
            {:else}
              <image
                xlink:href={svgName}
                width="90%"
                style="transform:translate({imgWidth/2-(imgWidth*0.9)/2}px, {(innerHeight/2)-(imgHeight/2)/2}px)"
              />
            {/if}
            <!-- <image xlink:href="./public/svg/{svgName}.svg" width="100%" /> -->
            {#if value === 1}
              <Arrow x1={175} x2={140} y1={40} y2={30} flipAngle={true} />
              {#each "At 2.70 $/hour, // Nevada has the // highest median // prison wage".split("//") as substring, i}
                <text
                  class="annotation"
                  x="150"
                  y={60 + i * 14}
                  dx="10"
                  fill="b"
                  >{substring}
                </text>
              {/each}
            {/if}

            {#if value === 2}
              <Arrow x1={0} x2={0} y1={0} y2={0} />
              {#each "With a median prison wage // of 2.70 $/hour incarcerated // workers in Nevada earn 7.8 // $/hour less than Nevada // workers who earn the state // mandated minimum wage // of 10.50 $/hour".split("//") as substring, i}
                <text
                  class="annotation"
                  x="180"
                  y={225 + i * 14}
                  dx="10"
                  fill="b"
                  >{substring}
                </text>
              {/each}
            {/if}

            {#if value === 4}
              <Arrow x1={670} x2={620} y1={550} y2={590} />
              {#each "Incarcerated workers // in Arkansas, Georgia, // and Texas earn 0 $/hour".split("//") as substring, i}
                <text
                  class="annotation"
                  x="600"
                  y={500 + i * 14}
                  dx="10"
                  fill="b"
                  >{substring}
                </text>
              {/each}
            {/if}

            {#if value === 6}
              <Arrow x1={40} x2={90} y1={570} y2={640} flipAngle={true} />
              {#each "In Arkansas, Georgia, // and Texas, prison // labor is done for free. //  Incarcerated people //cannot earn a dollar // worth of income in // these states".split("//") as substring, i}
                <text class="annotation" x="0" y={470 + i * 14} dx="10" fill="b"
                  >{substring}
                </text>
              {/each}
            {/if}

            {#if value === 7}
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
            {/if}

            {#if value === 8}
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
            <!-- </svg>
                              </svg></svg
                            ></svg
                          ></svg
                        >
                      </svg>
                    </svg></svg
                  >
                </svg>
              </svg>
            </svg> -->
            </g>
          </svg>
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
    <section>
      <Outro />
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
    font-family: "Roboto Flex", sans-serif;
  }

  .hero h2 {
    margin-top: 0;
    font-weight: 200;
    font-family: "Roboto Flex", sans-serif;
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
    z-index: 1;
  }

  .section-container {
    margin-top: 1em;
    text-align: center;
    /* transition: background 100ms; */
    display: flex;
  }

  .step {
    height: 90vh;
    display: flex;
    place-items: center;
    justify-content: center;
    z-index: 100;
    color: #213547;
  }

  .step-content {
    font-size: 1rem;
    background: #fbf9ea;
    color: #213547;
    border-radius: 5px;
    padding: 0.5rem 1rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    /* transition: background 500ms ease; */
    box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.2);

    width: 75%;
    margin: auto;
    max-width: 500px;
    font-family: "Roboto Flex", sans-serif;
    z-index: 100;
    color: #213547;
  }

  .step.active .step-content {
    background: #fbf9ea;
    color: #213547;
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
