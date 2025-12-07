# AWS CLI - ECR commands

Create a repository
-------------------------------------
`aws ecr create-repository
    --repository-name <repository-name>
    --region <region>
`
-------------------------------------
<br>

Authenticate to your default registry
-------------------------------------
`aws ecr get-login-password
    --region <region>
    | docker login --username AWS --password-stdin <registry-uri>
`
-------------------------------------
<br>

Push an image to ECR
-------------------------------------
List images: `docker images` <br>
Tag image to repository: `docker tag <image>:<tag> <registry-uri>/<repository-name>:<tag>` <br>
Push image: `docker push <registry-uri>/<repository-name>:<tag>`
-------------------------------------
<br>

Pull an image from ECR
-------------------------------------
`docker pull <registry-uri>/<repository-name>:<tag>`

-------------------------------------
<br>

Delete an image
-------------------------------------
`aws ecr batch-delete-image 
    --repository-name <repository-name> 
    --image-ids imageTag=<tag>
    --region <region>
`
-------------------------------------
<br>

Delete a repository
-------------------------------------
`aws ecr delete-repository 
    --repository-name <repository-name> 
    --region <region> 
    --force
`
-------------------------------------