<template>
	<div class="todoListContainer">
		<div class="heading">
			<h1 id="title">Todo List</h1>
			<add-item-form />
			
		</div>
		<list-view/>
	</div>
</template>			

<script>
import addItemForm from "./addItemForm"
import listView from "./listView"
	 export default {
		components: {
			addItemForm,
			listView
		}
	 }
 </script> 

<style scoped>
 .todoListContainer {
 	width:350px;
 	margin: auto;
 }	

 .heading{
 	background: #e6e6e6;
 	padding:10px;
 }

#titel {
	text-align: center;
}


</style>