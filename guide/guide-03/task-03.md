## Build Docker images

## Create a source code repository

1. Download sample source code from Cloud Shell
```
cd ~
wget https://gke-spinnaker.storage.googleapis.com/sample-app-v2.tgz
```

2. Extract the source code.

```
tar xzfv sample-app-v2.tgz
```

3. Change directory to source code

```
cd sample-app
```

4. Set username and email address for Git commits in this repository

```
git config --global user.email "[EMAIL_ADDRESS]"
git config --global user.name "[USERNAME]"
```

5. Perform initial commit to the source code repository

```
git init
git add .
git commit -m "Initial commit"
```

6. Create a repository to host your code.

```
gcloud source repos create sample-app
git config credential.helper gcloud.sh
```

7. Remotely add newly created repositories

```
export PROJECT=$(gcloud info --format='value(config.project)')
git remote add origin https://source.developers.google.com/p/$PROJECT/r/sample-app
```

8. Push code to the master branch of the new repository

```
git push origin master
```

9. Make sure you can see the source code in the console

```

```

Syntax highlighting

``` js
var foo = function (bar) {
  return bar++;
};

console.log(foo(5));
```
