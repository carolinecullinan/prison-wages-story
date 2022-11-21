<script>
    import { range, 
             scaleLinear, 
             max, 
             min } 
             from 'd3'

    let rangeOfNumbers = range(987,1087,1)
    
    let data = rangeOfNumbers.map((d, i)=>{
        return {
            index : i,
            element : d,
            x : Math.random() * (Math.random() * 1000), 
            y : Math.random() * 1000
        }
    })

    console.log(rangeOfNumbers)
    console.log(data)
</script>

<div  class="container">

    <svg>
        <!-- <g> -->
            {#each data as d, i}
                {#if Math.random() > 0.5}
                    <rect 
                    x={d.x}
                    y={d.y * 2}
                    width={Math.random() * 150}
                    height={Math.random() * 150}
                    fill='orange'
                    stroke='pink'
                    stroke-width = {Math.random() * 1.5}
                    >
                    </rect>
                {:else}
                    <rect
                    x={d.x * 2} 
                    y={d.y}
                    width={Math.random() * 150}
                    height={Math.random() * 150}                    
                    fill='pink'
                    stroke='orange'
                    stroke-width = {Math.random() * 1.5}
                    >
                </rect>
                {/if}
            {/each}
        <!-- </g> -->
    </svg>
</div>


<style>
    .container {
        background-color: aquamarine;
        width: 80vw;
        height: 60vh
    }

    svg {
        width: 100%;
        height: 100%
    }
</style>