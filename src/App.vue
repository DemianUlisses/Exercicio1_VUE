<template>
	<div id="app" class="grid">
		<Header class="header" title="Exercício 1" />
		<NavMenu :items="menuItems" />
		<Sidebar :sidebarMenu="sidebar" />
		<Articles :articles="articles" />
	</div>
</template>

<script>
	import Header from './components/Header';
	import NavMenu from './components/NavMenu';
	import Articles from './components/Articles';
	import Sidebar from './components/Sidebar';

	export default {
		name: 'App',
		components: {
			Header,
			NavMenu,
			Articles,
			Sidebar,
		},
		data() {
			return {
				menuItems: [
					{
						text: 'Intro to Vue course',
						link:
							'https://www.vuemastery.com/courses/intro-to-vue-js/vue-instance/',
					},
					{ text: 'Get Started', link: 'https://vuejs.org/v2/guide/' },
					{ text: 'GitHub', link: 'https://github.com/vuejs/vue' },
				],
				articles: [
					{
						title: 'Approachable',
						text:
							'Already know HTML, CSS and JavaScript? Read the guide and start building things in no time!',
					},
					{
						title: 'Versatile',
						text:
							'An incrementally adoptable ecosystem that scales between a library and a full-featured framework.',
					},
					{
						title: 'Performant',
						text:
							'20KB min+gzip Runtime. Blazing Fast Virtual DOM. Minimal Optimization Efforts',
					},
				],
				sidebar: [
					{ text: 'Core Docs', link: 'https://vuejs.org' },
					{ text: 'Forum', link: 'https://forum.vuejs.org' },
					{ text: 'Community', link: 'https://chat.vuejs.org' },
					{ text: 'Twitter', link: 'https://twitter.com/vuejs' },
					{ text: 'News', link: 'https://news.vuejs.org' },
				],
			};
		},
	};
</script>

<style>
	* {
		text-decoration: none;
	}
	a:hover {
		text-decoration: underline;
	}
	.li-menu {
		display: inline;
		color: #fff;
		text-decoration: none;
		padding: 4px 4px 4px;
	}
	#app {
		font-family: Avenir, Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
		margin-top: 60px;
	}
	.header {
		grid-area: header;
	}
	.navmenu {
		grid-area: navmenu;
	}
	.article {
		grid-area: article;
	}
	.sidebar {
		grid-area: sidebar;
	}
	.grid {
		margin: 0px;
		display: grid;
		grid-template-columns: 1fr 0.2fr;
		grid-template-rows: auto auto 1fr;
		grid-template-areas:
			'header header'
			'navmenu navmenu'
			'article sidebar';
		grid-gap: 1rem;
		height: 100vh;
	}
</style>
