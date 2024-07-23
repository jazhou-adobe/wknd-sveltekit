<script>
    import AemImage from '$lib/components/AemImage.svelte';

    export let _path;
    export let href;
    export let title;
    export let price;
    export let duration;
    export let imageSrc;
    export let itemId;
    export let showDetails = true;

    // const aboveFold = ['Surf Camp', 'Beervana in Portland'].includes(title);
    const aboveFold = imageSrc.includes("bali-surf-camp");
  </script>

  <div class="group relative" itemscope data-aue-type='reference' data-aue-filter='cf' data-aue-resource={itemId}>
    <div class="w-full h-full bg-gray-200 rounded-md overflow-hidden group-hover:opacity-75 lg:h-80 lg:aspect-none">
      <a href={href}>
        <AemImage
          src={imageSrc}
          alt={title}
          width={542}
          height={605}
          priority={aboveFold}
          loading={aboveFold ? 'eager' : 'lazy'}
          sizes="50vw"
          clazz="w-full h-full object-center object-cover lg:w-full lg:h-full"
          data-aue-prop='primaryImage'
          data-aue-type='media'
        />
      </a>
    </div>
    {#if showDetails}
    <div class="mt-1 pt-2 flex h-7">
      <p class="text-sm text-gray-500" data-aue-prop='tripLength' data-aue-type='text'>{duration}</p>
      <p class="flex-grow text-sm font-medium text-gray-900"></p>
      <p class="text-sm font-medium text-gray-900" data-aue-prop='price' data-aue-type='text'>{price}</p>
    </div>
    <h3 class="font-semibold text-gray-700 h-7">
      <a href={href}>
        <div data-aue-prop='title' data-aue-type='text'>
<!--          <span aria-hidden="true" class="absolute inset-0"></span>-->
          {title}
        </div>
    </a>
  </h3>
    {/if}

  </div>
