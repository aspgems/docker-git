# docker-git
Docker container to run git commands without needing to install git

## Motivation
If you want like to have development environment the most agnostic possible,
then you do not like to install development tools... This image helps you to
achieve this by providing dockerized git command

## Instructions
You can use this container by running the following command fron the root of your application

```bash
docker run --rm -it -v $(pwd):/repo -v ~/.ssh/id_rsa:/root/.ssh/id_rsa aspgems/git
```

If you want, for example, clone a repo, you should do something like the following

```bash
docker run --rm -it -v $(pwd):/repo -v ~/.ssh/id_rsa:/root/.ssh/id_rsa aspgems/git clone <your_repo_url>
```

**Configuring your public key:** This assumes that your id_rsa file resides in
~/.ssh/id_rsa. If you have your public key in other location, you should change that route.

**File permissions:** The files generated under vendor/bundle will belong to root user. You may need the ownership of this directory to match your user.

```bash
sudo chown -R your_user:your_group vendor/bundle
```
