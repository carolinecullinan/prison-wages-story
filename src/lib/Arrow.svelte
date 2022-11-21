<script>
    export let x1, x2, y1, y2, flipAngle=false, stroke="black";

    const buildArcH = (x1, x2, y1, y2, flipAngle) => {
        let r = innerWidth>500?Math.abs(x2 - x1)*(-0.7):Math.abs(x2 - x1)*1.2;  
        let path;
        if (flipAngle === true) {
            path=`M${x1} ${y1} A ${r},${r} 0 0,${0} ${x2},${y2}`;
        } else if (flipAngle === false) {
            path=`M${x1} ${y1} A ${r},${r} 0 0,${1} ${x2},${y2}`;
        }
        return path
    }
    let marker_id = `arrowhead-${Math.floor(Math.random() * 1e4)}`;
    $: marker_url = `url("#${marker_id}")`;
</script>
<g>
    <path 
    marker-end={marker_url}
    d="{buildArcH(x1,x2,y1,y2,flipAngle)}"
    fill="none"
    stroke={stroke}
    stroke-width="1"
    />
    <defs>
        <marker
          id={marker_id}
          viewBox="-10 -10 20 20"
          markerWidth="17"
          markerHeight="17"
          orient="auto"
        >
          <path class="marker" d="M-4,-4 L 0,0 L -4,4" style="fill: none; stroke: grey;stroke-linecap: round"/>
        </marker>
      </defs>
</g>