<script>
export let state;
export let variant;
export let dismissable;
export let text;
export let show;

const handleDismiss = (event) => {
    if (typeof event !== KeyboardEvent && event.key !== 'Escape') return
    show = false
}
</script>
{#if show}
<article class="alert" data-state="{state}" data-type="{variant}" {dismissable}>
    <div class="alert-icon"><svg data-icon="info-sign" viewBox="0 0 16 16"><path d="M8 0C3.58 0 0 3.58 0 8s3.58 8 8 8 8-3.58 8-8-3.58-8-8-8zM7 3h2v2H7V3zm3 10H6v-1h1V7H6V6h3v6h1v1z" fill-rule="evenodd"></path></svg></div>
    <div class="alert-text">
        {{text}}
    </div>
    <div class="alert-dismiss" on:click={handleDismiss}><svg data-icon="cross" viewBox="0 0 16 16"><path d="M9.41 8l3.29-3.29c.19-.18.3-.43.3-.71a1.003 1.003 0 00-1.71-.71L8 6.59l-3.29-3.3a1.003 1.003 0 00-1.42 1.42L6.59 8 3.3 11.29c-.19.18-.3.43-.3.71a1.003 1.003 0 001.71.71L8 9.41l3.29 3.29c.18.19.43.3.71.3a1.003 1.003 0 00.71-1.71L9.41 8z" fill-rule="evenodd"></path></svg></div>
</article>
{/if}