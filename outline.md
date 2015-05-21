# Goals
## Docker 
- have a clear understanding of what Docker _is_
- know the core vocab and concepts
- have a clearer idea of where Docker is a good fit for your problems
    * apps
    * tools
    * larger systems
- package simple single proc apps into images -> run containers
- make simple Dockerfiles
- be able compose and manage a set of containers
- know how to decompose a system into a set of containers
- be able to log, troubleshoot and monitor

## Kubernetes
- have a clear understanding of what Kubernetes _is_
- know the core vocab and concepts
- have a clearer idea of where Kubernetes is a good fit for your problems
- know how to compose a system from a set of containers

## Both
- know how to manage the lifecycle of dockerized/kub'd app
- know how where the solid ground and shifting sands are


# Morning 8:30 - 12:00
- 8:30 Introductions and [Setup](setup.md)

    * teaching philosophy
        - a few presentation sections for context but mostly:
        - active recall / free range exercises rather than lectures
        - lots of discussion and questions
        - pairs and lots of class interaction
	
    * student backgrounds and expectations
	* goals
    

- 9:20 [Basic Docker Usage](basic-docker.md)
simple example to play with basic commands and explore
feel out what they really know and need to learn

- 9:30 [What _is_ Docker?](docker-building-blocks.md)
    * elephant and the blind men
    * better isolation of procs
    * alternative to heavier vms
    * distribution mechanism
    * didn't LXC provide all that?
    * what's new about it?
        - layered file system
        - polish
        - _huge_ community
        - consistent shape of packaged/running apps
    * How can we use it?

- [Docker build files](docker-build-files.md)
- [Docker Compose](docker-compose.md)
- [Docker Volumes](docker-volumes.md)
- [Docker Networking](docker-networking.md)


# Lunch 12:00-1:00

# Afternoon 1:00-5:00
- 1:00-1:30 exercise: docker + config management

Use your favourite config management tool to do the equivalent of the
docker compose example: 3 nginx + 1 haproxy