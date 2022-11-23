<script>
</script>

<div class="grayline" />
<h3>METHODOLOGY</h3>
<div class = 'centerParagraph'>
   <p>The analysis behind this visual essay makes use of data from the <a
    href="https://www.prisonpolicy.org/"
    target="blank">Prison Policy Initiative</a>, the Human Rights Defense Center’s <a
    href="https://www.prisonphonejustice.org/" target="blank">Prison Phone Justice</a> campaign, <a
    href="https://worthrises.org/"
    target="blank">Worth Rises</a>, the <a
    href="https://www.dol.gov/"
    target="blank">United States Department of Labor</a>, the <a
    href="https://www.bop.gov/"
    target="blank">Federal Bureau of Prisons</a>, <a
    href="https://walkenhorsts.com/landing"
    target="blank">Walkenhorst’s</a>, <a
    href="https://orders.tigercommissary.com/Services/Default.aspx" target="blank">Tiger Commissary Services Inc.</a>, and <a
    href="https://www.accesscatalog.com/" target="blank">Access Securepak</a>.  <br><br>Datasets pertaining to prison phone rates were manually crafted via consultation with prison phone rate data made available by both the Human Rights Defense Center and Worth Rises.  Datasets pertaining to prison canteen prices were also manually crafted via a sampling of publicly available prison commissary lists from a variety of aforementioned sources.  With the Python programming language, all data was  wrangled, merged, cleaned, and analyzed.  Javascript (i.e., plot.js, Observable) was used to summarize and visualize key findings in an <a
    href="https://observablehq.com/@carolinecullinan/whats-a-dollar-cost" target="blank">Observable notebook</a>.  Adobe Illustrator was then used to artistically transform (i.e., draw) all data visualizations into more powerful storytelling elements.  Data and analysis related to this piece can be found on <a
    href="https://github.com/carolinecullinan/prison-wages" target="blank">Github</a>.<br><br>This webpage has been built with the <a
    href="https://svelte.dev/" target="blank">Svelte</a> framework.  The scrollytelling functionality of this piece was achieved using the Svelte implementation of <a
    href="https://twitter.com/russellviz" target="blank">Russel Samora</a>’s <a
    href="https://github.com/russellsamora/scrollama" target="blank">Scrollama.js</a> and <a
    href="https://www.connorrothschild.com/ " target="blank">Connor Rothschild</a>’s fantastic <a
    href="https://www.connorrothschild.com/post/svelte-scrollytelling" target="blank">tutorial</a>.  The code behind this application can be found on <a
    href="https://github.com/carolinecullinan/prison-wages-story" target="blank">Github</a>.</p>
</div>
<style>
    .grayline {
        border-top: 2px solid grey;
        height: 2.5 px;
        width: auto;
    }

    .centerParagraph {
        text-align: center;
        max-width: 500px;
        margin: auto;
        color: #213547;
    }
</style>
