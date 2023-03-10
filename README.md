# Portfolio
Portfolio project based on Gatsby.

## Prerequisite
> Install `nvm`
>
> Use `nvm` to install `node`
>
> Require `node>=18`
>

```
sudo npm install -g gatsby-cli
gatsby --version
npm run develop
```

## Deploy
Subject to potential overload on AWS t2.micro EC2 instance, I would rather to upload the built project directly.

### 1. Build the project

```
npm run build
```

### 2. Remove cache and node relatives

```
rm -rf .cache node_modules package-lock.json
```

### 3. Archive and compress

```
cd ..
tar -czf archive.tar.gz portfolio_gatsby
```

### 4. Upload to server and extract directory

```
sftp myAWSEC2server
cd /path/to/project
put archive.tar.gz
exit
--------------------
cd /path/to/project
tar -xf archive.tar.gz
```

### 5. Restart Apache

```
sudo systemctl restart apache2
```

