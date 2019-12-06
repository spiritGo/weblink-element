<template>
	<div class="home">
		<div v-for="(item, index) in data" :key="index" class="margin" @click="goWeb" :data-path="item.url">
			<el-button :type="index%2 == 0 ? 'primary':'danger'" icon="el-icon-position">{{ item.title }}</el-button>
		</div>
	</div>
</template>

<script>
	// @ is an alias to /src
	import data from "../json/data.js"
	export default {
		data() {
			return {
				data: data
			}
		},
		methods: {
			goWeb(e) {
				location.href = e.currentTarget.dataset.path;
			}
		}
	}
</script>
<style lang="scss" scoped>
	.home {
		background-color: #303133;
		max-width: 1200px;
		box-sizing: border-box;
		margin: 50px auto;
		padding: 10px;
		display: flex;
		flex-wrap: wrap;
		border-radius: 2px;
	}

	.margin {
		margin: 5px;
		box-shadow: 0 2px 4px #999;
		border-radius: 6px;
	}
</style>
