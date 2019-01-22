<template>
	<div class="container">
		<table class="table table-striped mt-4">
		  <thead>
		    <tr>
		      <th scope="col">USER ID</th>
		      <th scope="col">ID</th>
		      <th scope="col">TITLE</th>
		      <th scope="col">BODY</th>
		    </tr>
		  </thead>
		  <tbody>
		    <tr v-for="post in posts" :key="post.id">
		      
		      <td>{{ post.userId }}</td>
		      <td>{{ post.id }}</td>
		      <td>{{ post.title }}</td>
		      <td>{{ post.body }}</td>
		    </tr>
		  </tbody>
		</table>

	</div>

</template>

<script>
	import axios from 'axios'

	export default{
		name: 'PostsExample',
		data(){

			return{

				posts:  [

				
				]
			}
		},

		created(){
			axios.get('https://jsonplaceholder.typicode.com/posts').then(posts => {

				this.posts = posts.data

			});
		}
	}
</script>

<style>

<script>