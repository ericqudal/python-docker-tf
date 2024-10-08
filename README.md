Steps to Deploy to ECS
1. **Build the Docker Image:**
   ```bash
   docker build -t fastapi-poet .
   ```

2. **Tag and Push to a Container Registry (e.g., AWS ECR):**
   ```bash
   aws ecr create-repository --repository-name fastapi-poet
   docker tag fastapi-poet:latest <AWS_ECR_URL>:latest
   docker push <AWS_ECR_URL>:latest
   ```

3. **Apply the Terraform Configuration:**
   ```bash
   terraform init
   terraform apply -f ecs.tf
   ```
