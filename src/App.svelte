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
    import Method from "./lib/Method.svelte";





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
    "<p>However, these states don’t compensate incarcerated workers at all for their labor.  Folks incarcerated in <span style = 'color: #ff9f3f; font-weight: 600'>Arkansas</span>, <span style = 'color: #ff9f3f; font-weight: 600'>Georgia</span>, and <span style = 'color: #ff9f3f; font-weight: 600'>Texas</span> must work for free, which means that they earn <span style = 'color: #7695c4; font-weight: 600'>100% less</span> than non-incarcerated people who earn the government mandated minimum wage in each respective state.</p>",
    "<p>Now, with this information, we can try to understand what a dollar costs in the US prison system in terms of <span style = 'color: #7695c4; font-weight: 600'>labor</span>. In each state, how many hours of labor equate to $1.00 in prison wages? </p>",
    "<p> Given the fact that people in <span style = 'color: #ff9f3f; font-weight: 600'>Arkansas</span>, <span style = 'color: #ff9f3f; font-weight: 600'>Georgia</span>, and <span style = 'color: #ff9f3f; font-weight: 600'>Texas</span> aren’t financially compensated at all for their prison labor, folks incarcerated in these states can’t even earn a dollar.  These people have to work for free.</p>",
    "<p>However, in considering states that provide some financial compensation for prison labor, we can see that a dollar costs the most in <span style = 'color: #ff9f3f; font-weight: 600'>Alabama</span>. With a median prison wage of 0.12 $/hour, incarcerated people in Alabama must conduct <span style = 'color: #7695c4; font-weight: 600'>8.33 hours</span> of labor at the median prison wage in order to earn a single dollar.</p>",
    "<p>On the other hand, this same $1.00 is least expensive in the state of <span style = 'color: #ff9f3f; font-weight: 600'>Nevada</span>. Here, with a median prison wage of 2.70 $/hour, incarcerated people in Nevada have to work about <span style = 'color: #7695c4; font-weight: 600'>0.37 hours</span> for that same $1.00 worth of earnings.<br><br>At a glance, it may appear as if incarcerated people in Nevada are subjected to fairer prison wages when compared to other US states. However, for that same $1.00 worth of earnings, these workers have to work about <span style = 'color: #7695c4; font-weight: 600'>16 and a half minutes longer</span> than non-incarcerated Nevada workers who earn the government mandated minimum wage. In other terms, this means that in Nevada, incarcerated folks have to work <span style = 'color: #7695c4; font-weight: 600'>289% more</span> for that same $1.00 than non-incarcerated folks.</p>",
    "<div style='text-align:center;width:100%;font-size:50px'>.  .  .</div><br><p>So, now that we understand the cost of a dollar in terms of US prison labor, let's try to understand the purchasing power of such prison labor. What can these hard-worked hours buy? To get a better idea about the amount of labor that incarcerated folks need to perform in different US states in order to be able to afford different items that help them meet some of their basic needs, this quick-dive considers the average cost of a <span style = 'color: #7695c4; font-weight: 600'>15-minute </span> (in-state) <span style = 'color: #7695c4; font-weight: 600'>phone call </span>, a tube of <span style = 'color: #7695c4; font-weight: 600'>toothpaste</span>, a pack of <span style = 'color: #7695c4; font-weight: 600'>rice</span>, and an ink <span style = 'color: #7695c4; font-weight: 600'>pen</span>.</p>",
    "<p>Given the median prison wage and the average cost of prison phone time across states, the hours of labor that incarcerated workers must perform for a <span style = 'color: #7695c4; font-weight: 600'>15-minute phone call</span> with loved ones on the outside was calculated.</p>",
    "<p>While incarcerated people in <span style = 'color: #ff9f3f; font-weight: 600'>Connecticut</span> and <span style = 'color: #ff9f3f; font-weight: 600'>California</span> can freely call loved ones without any charge for the minutes spent on the phone, folks incarcerated in other states aren’t as fortunate. In <span style = 'color: #ff9f3f; font-weight: 600'>Arkansas</span>, <span style = 'color: #ff9f3f; font-weight: 600'>Georgia</span>, and <span style = 'color: #ff9f3f; font-weight: 600'>Texas</span>, where prison labor is conducted for free, incarcerated people can't even buy their own phone time with an earned wage. But in only considering states where incarcerated people are financially compensated for their labor, we can see that those incarcerated in <span style = 'color: #ff9f3f; font-weight: 600'>Pennsylvania</span> are worst off. Here, incarcerated people have to work about <span style = 'color: #7695c4; font-weight: 600'>29 and half hours</span> at the median prison wage just to be able to afford 15 minutes of phone time.<br><br></p>",
    "<p>And hygiene? Surely incarcerated people shouldn’t be subjected to hard-labor just to be able to afford something as essential to personal hygiene as a tube of <span style = 'color: #7695c4; font-weight: 600'>toothpaste</span>, right?</p>",
    "<p>While incarcerated people earning the median prison wage in <span style = 'color: #ff9f3f; font-weight: 600'>Maine</span> may “only” need to work roughly <span style = 'color: #7695c4; font-weight: 600'>2 hours and 15 minutes</span> to be able to afford a typical tube of toothpaste from their prison canteen, those incarcerated in <span style = 'color: #ff9f3f; font-weight: 600'>Alabama</span> prisons have to work a staggering <span style = 'color: #7695c4; font-weight: 600'>33 hours</span> at the median prison wage for that same tube of toothpaste. This basically means that in Alabama, incarcerated folks have to put in more than <span style = 'color: #7695c4; font-weight: 600'>4 full 8-hour work days </span> before they can afford to keep their teeth clean. </p>",
    "<p>And when it comes to food, incarcerated people looking to supplement their prison cafeteria diet with additional food items can also do so at a laborious cost. Let's consider a typical pack of <span style = 'color: #7695c4; font-weight: 600'>rice</span>, for example.<br><br>While not every state prison commissary sampled made rice  available for purchase (e.g., <span style = 'color: grey; font-weight: 600'>Maine</span> and <span style = 'color: grey; font-weight: 600'>Montana</span>), incarcerated folks across the US seem to have more or less general access to this food item. However, prices for commissary prison rice also appear to vary widely across states.</p>",
    "<p>Once again, incarcerated folks in <span style = 'color: #ff9f3f; font-weight: 600'>Alabama</span> have to work the most at the median prison wage to be able to afford this product. A typical pack of rice for people incarcerated in this state costs about <span style = 'color: #7695c4; font-weight: 600'>11 hours and 40 minutes</span> of labor. Contrastingly, with about <span style = 'color: #7695c4; font-weight: 600'>an hour</span> of labor at the median prison wage, folks incarcerated in <span style = 'color: #ff9f3f; font-weight: 600'>New Jersey</span> can purchase this same pack of rice.</p>",
    "<p>And finally, the ink <span style = 'color: #7695c4; font-weight: 600'>pen</span>. Crucial for learning, self-expression, and communicating with others,  the pen is an indispensable tool for day-to-day life both inside and outside of prison. So as valuable as this miscellaneous item is, what’s it cost for those incarcerated?</p>",
    "<p>Unfortunately, not every state prison commissary sampled made ink pens available for purchase (e.g., <span style = 'color: grey; font-weight: 600'>Montana</span>, <span style = 'color: grey; font-weight: 600'>Nebraska</span>, and <span style = 'color: grey; font-weight: 600'>Utah</span>). However with these pen-less states and <span style = 'color: #ff9f3f; font-weight: 600'>Arkansas</span>, <span style = 'color: #ff9f3f; font-weight: 600'>Georgia</span>, and <span style = 'color: #ff9f3f; font-weight: 600'>Texas</span> aside (i.e., states where incarcerated folks aren’t paid for their labor), the hours of work that incarcerated people have to perform at the median prison wage to be able to afford the average prison commissary ink pen was calculated across the US.<br><br>While incarcerated folks in <span style = 'color: #ff9f3f; font-weight: 600'>Minnesota</span> may have to put in only <span style = 'color: #7695c4; font-weight: 600'>12 minutes</span> of labor to be able to purchase an ink pen, folks incarcerated in <span style = 'color: #ff9f3f; font-weight: 600'>Oklahoma</span> have to put in more than <span style = 'color: #7695c4; font-weight: 600'>16 hours</span> of work for that same writing utensil. And this basically means that the difference between being incarcerated in Oklahoma instead of Minnesota is more than <span style = 'color: #7695c4; font-weight: 600'>8030%</span> more labor just to be able to write a letter home to your loved ones.</p>",
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

  $: transform = blur.includes(value)||
                 pennyStacks.includes(value)||
                 pennyStacksNV_gap.includes(value)||
                 pennyStacksWS_stateMin.includes(value)||
                 pennyStacksWS_gap.includes(value)||
                 laborPerPhone15.includes(value)?
                  `translate(${imgWidth/2-(imgWidth*0.9)/2}, ${(innerHeight-(imgHeight*0.9))/2})`:
                 phoneIcon.includes(value)||
                 toothpasteIcon.includes(value)||
                 riceIcon.includes(value)||
                 penIcon.includes(value)?
                  `translate(${imgWidth/2-(imgWidth*0.9)/2}, ${(innerHeight/2)-(imgHeight/2)/2})`:
                 laborPerDollarBlur.includes(value)||
                 laborPerDollar.includes(value)?
                  `translate(${imgWidth/2-(imgWidth*.89)/2}, ${(innerHeight-(imgHeight*1.2))/2})`:
                 laborPerToothpaste.includes(value)||
                 laborPerRice.includes(value)||
                 LaborPerPen.includes(value)?
                  `translate(${imgWidth/2-(imgWidth*.91)/2}, ${(innerHeight-(imgHeight*.99))/2})`:
                  `translate(${imgWidth/2-(imgWidth*0.9)/2}, ${(innerHeight-(imgHeight*1.2))/2})`;

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
  {#if laptop}
    <section>
      <Intro />
    </section>
    <section>
      <!-- <div class="hero" /> -->
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
        <div class="sticky">
         
          <svg width={imgWidth} height={imgHeight}>
            <g transform={transform}>
              <image
                xlink:href={svgName}
                width="90%"
              />
              <!-- style={transform} -->

              <!-- width="90%" -->

            {#if value === 1}
              <Arrow x1={140} x2={50} y1={90} y2={90} flipAngle={true} />
              {#each "At 2.70 $/hour, // Nevada has the // highest median // prison wage".split("//") as substring, i}
                <text
                  class="annotation"
                  x="140"
                  y={90 + i * 14}
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
                  x="150"
                  y={200 + i * 14}
                  dx="10"
                  fill="b"
                  >{substring}
                </text>
              {/each}
            {/if}

            {#if value === 4}
              <Arrow x1={650} x2={450} y1={500} y2={590} />
              {#each "Incarcerated workers // in Arkansas, Georgia, // and Texas earn 0 $/hour".split("//") as substring, i}
                <text
                  class="annotation"
                  x="600"
                  y={500 + i * 14}
                  dy="-40"
                  fill="b"
                  >{substring}
                </text>
              {/each}
            {/if}

            {#if value === 6}
              <Arrow x1={680} x2={570} y1={620} y2={680} />
              {#each "In Arkansas, Georgia, // and Texas, prison // labor is done for free. //  Incarcerated people //cannot earn a dollar // worth of income in // these states".split("//") as substring, i}
                <text class="annotation" x="680" y={520 + i * 14} dx="-50" fill="b"
                  >{substring}
                </text>
              {/each}
            {/if}

            {#if value === 7}
              <Arrow x1={680} x2={610} y1={620} y2={670} />
              {#each "In Alabama, incarcerated// people have to work,// on average, 8 hours// and 20 miuntes for// a dollar of earnings".split("//") as substring, i}
                <text
                  class="annotation"
                  x="600"
                  y={550 + i * 14}
                  dx="10"
                  fill="b"
                  >{substring}
                </text>
              {/each}
            {/if}

            {#if value === 8}
              <Arrow x1={270} x2={100} y1={200} y2={100} flipAngle={true}/>
              {#each "On average, incarcerated// people in Nevada have// to work about 22 minutes// to earn a single dollar".split("//") as substring, i}
                <text
                  class="annotation"
                  x="210"
                  y={215 + i * 14}
                  dx="10"
                  fill="b"
                  >{substring}
                </text>
              {/each}
            {/if}

            {#if value === 11}
            <Arrow x1={100} x2={60} y1={40} y2={20} flipAngle={true}/>
            {#each "Phone calls in // Connecticut // and California // are free.  ".split("//") as substring, i}
              <text
                class="annotation"
                x="100"
                y={50 + i * 14}
                dx="5"
                fill="b"
                >{substring}
              </text>
            {/each}

            <Arrow x1={80} x2={20} y1={500} y2={440} />
            {#each "Incarcerated people are not // paid for their labor // in Arkansas, Georgia, // and Texas, so their // hard-work can't buy // phone time".split("//") as substring, i}
              <text
                class="annotation"
                x="80"
                y={500 + i * 14}
                dx="10"
                fill="b"
                >{substring}
              </text>
            {/each}

            <Arrow x1={690} x2={710} y1={320} y2={405} />
            {#each "People incarcerated in // Pennsylvania have to // work almost 4 full 8-work // days in order to be able // to make a 15-minute // phone call ".split("//") as substring, i}
              <text
                class="annotation"
                x="550"
                y={270 + i * 14}
                dx="10"
                fill="b"
                >{substring}
              </text>
            {/each}

            
          {/if}

          {#if value === 13}
          <Arrow x1={130} x2={80} y1={30} y2={10} flipAngle={true}/>
          {#each "In Maine, the average // tube of toothpaste can // be bought with about 2 // hours and 15 minutes of // prison labor ".split("//") as substring, i}
            <text
              class="annotation"
              x="130"
              y={45 + i * 14}
              dx="0"
              fill="b"
              >{substring}
            </text>
          {/each}

          <Arrow x1={640} x2={690} y1={440} y2={540} />
          {#each "Prison canteen toothpaste // costs about 4 full 8-hour // work days worth // of labor in Alabama ".split("//") as substring, i}
            <text
              class="annotation"
              x="490"
              y={420 + i * 14}
              dx="10"
              fill="b"
              >{substring}
            </text>
          {/each}

        {/if}

        {#if value === 15}
          <Arrow x1={130} x2={95} y1={30} y2={10} flipAngle={true}/>
          {#each "New Jersey prison // canteen rice can be // purchased for about // an hour of prison labor".split("//") as substring, i}
            <text
              class="annotation"
              x="130"
              y={20 + i * 14}
              dx="5"
              fill="b"
              >{substring}
            </text>
          {/each}

          <Arrow x1={740} x2={700} y1={430} y2={500} />
          {#each "In Alabama, prison // canteen rice can be // purchased with about // 12 hours of prison // labor ".split("//") as substring, i}
            <text
              class="annotation"
              x="600"
              y={400 + i * 14}
              dx="10"
              fill="b"
              >{substring}
            </text>
          {/each}

        {/if}

        {#if value === 17}
        <Arrow x1={80} x2={50} y1={30} y2={10} flipAngle={true}/>
        {#each "With 12 minutes of prison work, // incarcerated people in Minnesota // can purchase an ink pen from the // prison canteen".split("//") as substring, i}
            <text
              class="annotation"
              x="80"
              y={35 + i * 14}
              dx="5"
              fill="b"
              >{substring}
            </text>
          {/each}

          <Arrow x1={690} x2={660} y1={390} y2={480} />
          {#each "In Alabama, incarcerated // people need to work // for roughly 16 hours // in order to be able //  to afford an ink pen".split("//") as substring, i}
            <text
              class="annotation"
              x="560"
              y={380 + i * 14}
              dx="0"
              fill="b"
              >{substring}
            </text>
          {/each}

        {/if}
            </g>
          </svg>
        </div>

      </div>
    </section>
    <section>
      <Outro />
    </section>
    <section>
      <Method />
    </section>
  {:else}
    <h2>
      This article has not been optimized for small screens, sorry! Please use
      full-screen mode or use a larger device. Thank you!
    </h2>
  {/if}
</main>

<style>


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
