1. Create a token for the action workflow so that it can authenticate with github for the repository. COPY THE TOKEN AFTER CREATION. ![[Pasted image 20230212122614.png]]
2. Create an environment for your github action where it can access the token, and add the token under *environment secrets*. The name you give to the secret is how you will access it in the workflow `yaml`. ![[Pasted image 20230212122909.png]]
3. 
4. In your workflow, use the `environment` tag to specify the environment that we created, and use the `env` tag to create a environment variable with the access token that our workflow will be able to use. Also specify the `remote origin` with the token. This is an example where we create a `hello world` file and push it to the repository.
   ```yaml
	name: Push File to Repo
		on: [workflow_dispatch]
		jobs:
		  render_document:
		    environment: 
		      name: <environment name> # using the created environment so that we can access the token
		    env:
		      GITHUB_TOKEN: ${{ secrets.<environment secret name> }} # creating a variable that will hold our token
		    runs-on: ubuntu-latest
		    steps:
		      - uses: actions/checkout@v3
		      - name: Commit and Push
		        run: |
			      echo "Hello World" > hw.txt
				  git config user.name github-actions
				  git config user.email github-actions@github.com
				  git add hw.txt
				  git commit -m 'Hello World' 
				  git remote set-url --push origin https://<profile name>:$GITHUB_TOKEN@github.com/<profile name>/<repo name>.git
				  git push
```