<script setup>
import FilterTabs from "../FilterTabs/FilterTabs.vue";
import PlusButton from "./PlusButton.vue";
import SearchBar from "./SearchBar.vue";
import ProfileDetails from "./ProfileDetails.vue";

function searchTriggered(value) {
	console.log("Search value: " + value);
}
function plusButtonClick() {
	console.log("PlusButton Clicked");
	return;
}
</script>

<template>
	<div class="header">
		<div class="header--top">
			<div>
				<h1 class="top--title">Projects</h1>
			</div>
			<SearchBar @search="searchTriggered" />
			<div class="top--right">
				<div class="right--icons">
					<div class="iconumsu"></div>
					<div class="iconumsu"></div>
					<div class="iconumsu"></div>
				</div>
				<ProfileDetails />
			</div>
		</div>
		<div class="header--bottom">
			<PlusButton @btnClick="plusButtonClick" />
			<FilterTabs />
		</div>
	</div>
</template>

<style scoped lang="scss">
.header {
	display: flex;
	flex-direction: column;
	gap: 28px;
	padding: 32px 30px;

	&--top {
		display: flex;
		align-items: center;
		justify-content: space-between;

		.top--title {
			margin: 0;
			line-height: 28px;
			color: #3c557a;

			font : {
				family: "Roboto";
				style: normal;
				weight: 500;
				size: 24px;
			}
		}

		.top--right {
			display: flex;
			justify-content: center;

			.right--icons {
				display: flex;
				align-items: center;
				gap: 2rem;

				div {
					height: 28px;
					width: 28px;
					background-color: red;
				}
			}
		}
	}

	&--bottom {
		display: flex;
		gap: 30px;
	}

}
</style>
