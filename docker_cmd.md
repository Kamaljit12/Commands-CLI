# 🐳 Docker Daily Use Commands

## ✅ Check Docker Installation

```bash
docker --version                      # Show Docker version
systemctl --user start docker-desktop # Start Docker Desktop (Linux)
✅ General Info
bash
Copy code
docker --version                # Show Docker version
docker info                     # Show system-wide info
docker help                     # List all docker commands
📦 Images: List / Pull / Remove
bash
Copy code
docker images                   # List local images
docker pull ubuntu              # Download image from Docker Hub
docker rmi ubuntu               # Remove an image
🛠️ Build from Dockerfile
bash
Copy code
docker build -t myapp:1.0 .     # Build image from Dockerfile in current directory
🚀 Run a Container
bash
Copy code
docker run hello-world                     # Run a test container
docker run -it ubuntu bash                 # Run Ubuntu interactively
docker run -d -p 8080:80 nginx             # Detached Nginx container on port 8080
🔄 Manage Containers: List / Stop / Start / Remove
bash
Copy code
docker ps                                 # List running containers
docker ps -a                              # List all containers
docker stop <container_id>               # Stop a running container
docker start <container_id>              # Start a stopped container
docker restart <container_id>            # Restart a container
docker rm <container_id>                 # Remove a container
📁 Volumes (For Data Persistence)
bash
Copy code
docker volume create myvolume             # Create a volume
docker volume ls                          # List volumes
docker volume rm myvolume                 # Remove volume
docker run -v myvolume:/data ubuntu       # Mount volume to container
🌐 Networking
bash
Copy code
docker network ls                         # List networks
docker network create mynet               # Create a network
docker run --network=mynet mycontainer    # Run container in specific network
🔍 Inspect / Logs / Exec
bash
Copy code
docker inspect <container_id>             # Detailed info about a container
docker logs <container_id>                # View container logs
docker exec -it <container_id> bash       # Access container shell
🧹 Cleanup (Free Up Space)
bash
Copy code
docker system prune                        # Remove stopped containers, unused images, etc.
docker container prune                     # Remove all stopped containers
docker image prune                         # Remove unused images
docker volume prune                        # Remove unused volumes
🛠️ Common Dev Usage
Mount a local folder:
bash
Copy code
docker run -v $(pwd):/app -w /app python python3 script.py
📦 Docker Compose (if using docker-compose.yml)
bash
Copy code
docker-compose up -d                      # Start services in background
docker-compose down                       # Stop and remove services
docker-compose logs -f                    # View logs
📚 BONUS: Useful Aliases
Add these to your ~/.bashrc or ~/.zshrc:

bash
Copy code
alias dps="docker ps"
alias dpa="docker ps -a"
alias dimg="docker images"
alias drm="docker rm"
alias drmi="docker rmi"
alias dexec="docker exec -it"
