<template>

<div>
<table class="table table-stripped mt-4">
	<thread>
		<tr>
			<tr>
				<th scope="col">name</th>
				<th scope="col">email</th>
			</tr>
	</thread>
	<tbody>
		<tr v-for="input in directory.edges" :key="input.id">
			<td>{{ input.node.username }}</td>
			<td>{{ input.node.email }}</td>
		</tr>
	</tbody>
</table>

</div>
</template>

<script>
  import axios from 'axios'
  export default{
  	name: 'CompanyData',
    data(){
      return {
      	directory: []
      }
    },
    async mounted () {
    	try {
    		var result = await axios({
    			method: 'POST',
    			url: 'https://noumenal.herokuapp.com/graphql/',
    			data: {
    				query: `
    				{
  users {
    edges {
      node {
        id
        username
        email
        isActive
        archived
        verified
        secondaryEmail
      }
    }
  }
}
					     
					       
					 
					
    				`
    			}
    		})
    		this.directory = result.data.data.users
    	} catch (error) {
    		console.error(error)
    	}
    }
  }
</script>

<style scoped>
</style>
