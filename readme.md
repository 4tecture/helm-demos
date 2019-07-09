# Demo Helm Repo

## Create a github repo to serve as chart repo
- Create a public GitHub repository
- `git clone <yourrepo>`
- `cd <yourrepo>`
- `git checkout -b gh-pages`

## Create the helm chart package
- `cd <chart folder of project>`
- `helm package <chartname>` 
- `mv <chartname>-<version>.tgz <yourrepo>`

## Create a repo index
- `cd <yourrepo>`
- `helm repo index . --url <your gh-pages url>`
- `git add *.*`
- `git commmit -m "my first chart repo upload"` 
- `git push --set-upstream origin gh-pages`

## Use your repo with helm
- `helm repo add <reponame> <repourl>`
- `helm install <reponame>/<chartname> --name=<your release name>`