1. Create GCP Compute Engine instance
    - Increase boot disk size (to be able to accomodate larger/more images)
    - Configure access scopes (to be able to write to artifact registry)
        - Storage `read-write` or Cloud Platform `enabled`
    - Configure firewall
        - Allow HTTP and HTTPS traffic
    - Add SSH key (useful to have to SSH into machine using IDE like VS Code)
2. Install Docker Engine on the GCE instance
    - https://docs.docker.com/engine/install/debian/ (use appropriate OS intructions)
    - https://docs.docker.com/engine/install/linux-postinstall/ (needed to use docker cli without `sudo`)
3. SSH into the compute instance
    - install docker extension (if using vs code, not necessary but helpful)
4. Determine base image
    - GCP base images can be found here: gcr.io/deeplearning-platform-release
5. Create Dockerfile and requirements (see example files)
6. Build image
7. Authenticate Docker on compute instance
    - Use cloud credential helper: https://cloud.google.com/artifact-registry/docs/docker/pushing-and-pulling
8. Create a image repository
    - https://cloud.google.com/artifact-registry/docs/docker/store-docker-container-images
9. Tag and push the image
    - https://cloud.google.com/artifact-registry/docs/docker/pushing-and-pulling
10. When creating a new user-managed notebook, select the Custom Container option when selecting environment