This repository is a central point for the Dockerfiles I use to test my Ansible roles.

## Motivation

1. I don't want to maintain a repo for each Docker image I need to test my Ansible roles.
2. I don't want to watch what happens on Docker Hub.
3. I'd like to run my tests on up-to-date images.
4. Docker Hub can sometimes be quite painful to use so I'd like to get rid of it.

Since Molecule is able to create the needed Docker images at each run, why not leverage this functionality to reach these goals ?

My Ansible roles contain a very simple `Dockerfile.j2` file (used by Molecule) that simply fetches a `Dockerfile` from this repo based on the Linux distribution "codename":
```jinja2
{{ lookup('url', 'https://raw.githubusercontent.com/Frzk/docker-ansible-images/main/' ~ item.image ~ '/Dockerfile', split_lines=False) }}
```

I think it's much easier to maintain this way, and I don't depend on Docker Hub anymore :)
