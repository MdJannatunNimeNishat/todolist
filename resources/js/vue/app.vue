<template>
	<div class="todoListContainer">
		<div class="heading">
			<h1 id="title">Todo List</h1>
			<add-item-form
				 v-on:reloadlist= "getList()"
			 />
			
		</div>
		<list-view
		 :items= "items"
		 v-on:reloadlist= "getList()"

		  />

	</div>
</template>			

<script>
import addItemForm from "./addItemForm"
import listView from "./listView"
	 export default {
		components: {
			addItemForm,
			listView
		},
		//data are getting from databage
		data: function () {
			return {
				items: [] //data from data base stores here.
			}
		},
		methods: {
			getList () { // this method getList grab the data from database
				axios.get('api/items')
				.then( response => {
					this.items = response.data // we initialling the items with data from database that we are getting. 
				})
				.catch ( error => {
					console.log(error);
				})

			}
		},
		created () {
			this.getList() ; // we call the getList method here. 
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

#title {
	text-align: center;
}


</style>