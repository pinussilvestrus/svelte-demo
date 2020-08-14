<script>
  import { onMount } from 'svelte';

  import { findIndex } from 'min-dash';

  import './index.scss';

  // variant A - normal button, alert click handler
  import App_A from './variants/VariantA';

  // variant B - blue button, alert click handler
  import App_B from './variants/VariantB';

  // variant C - blue button, black cat click handler
  import App_C from './variants/VariantC';

  const VARIANTS = ['A', 'B', 'C'];

  const DEFAULT_VARIANT = 'A';

  const toggleVariant = (variant) => {
    const found = findIndex(VARIANTS, v => v === variant);

    if (found < 0) {
      return active = VARIANTS[0];
    }
  
    active = variant;
    updateURL(variant);
  };

  const onNextVariant = () => {
    const found = findIndex(VARIANTS, v => v === active);

    if (found === VARIANTS.length - 1) {
      toggleVariant(VARIANTS[0]);
    } else {
      toggleVariant(VARIANTS[found + 1]);
    }
  };


  // state //////////
  let active = DEFAULT_VARIANT;


  // lifecycle //////////
  onMount(async () => {
    const variant = urlParam('variant');
    toggleVariant(variant);
  });


  // helpers //////////

  function updateURL(variant) {
    const newurl = `${window.location.protocol}//${window.location.host}${window.location.pathname}?variant=${variant}`;
    window.history.pushState({ path: newurl }, '', newurl);
  }

  function urlParam(name) {
    const results = new RegExp('[?&]' + name + '=([^&#]*)')
      .exec(window.location.href);

    return results && results[1] || DEFAULT_VARIANT;
  }

</script>

<div class="variant-badge" on:click={onNextVariant}>
  <span>{active}</span>
</div>

{#if active === 'A'}
  <div class="variant variant-a">
      <App_A />
  </div>
{/if}

{#if active === 'B'}
  <div class="variant variant-b">
      <App_B />
  </div>
{/if}

{#if active === 'C'}
  <div class="variant variant-c">
      <App_C />
  </div>
{/if}