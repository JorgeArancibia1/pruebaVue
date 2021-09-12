<template>
  <div id="app">
    <home />
  </div>
</template>

<script>
// @ is an alias to /src
import Home from './views/Home';

export default {
	name: 'Sidebar',
	components: { Home },
};
</script>
