<script>
	import Components from '$lib/components/compSelection/compSelection.svelte';
import Sidenavigation from '$lib/components/sideNavigation/sidenavigation.svelte';
</script>

<Sidenavigation
  navBarSource={[
    {
	  sidenavHeaderSource: 'Category-1',
      sidenavContentSource: [
        {  sidenavComponentSource: 'Component-1', link: '/' },
        { sidenavComponentSource: 'Component-2', link: '/'  },
        { sidenavComponentSource: 'Component-3', link: '/'  },
      ]
    },
    {
	  sidenavHeaderSource: 'Category-1',
      sidenavContentSource: [
        {  sidenavComponentSource: 'Component-1', link: '/' },
        { sidenavComponentSource: 'Component-2', link: '/'  },
        { sidenavComponentSource: 'Component-3', link: '/'  },
      ]
    },
    {
	  sidenavHeaderSource: 'Category-1',
      sidenavContentSource: [
        {  sidenavComponentSource: 'Component-1', link: '/' },
        { sidenavComponentSource: 'Component-2', link: '/'  },
        { sidenavComponentSource: 'Component-3', link: '/'  },
      ]
    },
  ]}
/>

<Components />
