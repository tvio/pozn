<template>
<div class="row">
    <div class="col-sm-12">
        <h3>Počet poznámek</h3>
    <div class="progress">
	    <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100"
        :style="{width:(pocet/maximum)*100 + '%'}">
	 {{pocet}} / {{maximum}}
	</div>
</div>	
</div>
</div>
</template>
<script>
export default {
    props:['pocet','maximum']
}
</script>