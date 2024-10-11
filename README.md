Create a Docker image and upload to Docker Hub:

Build a Docker image:

```
docker build -t antonpatsev/sentry-benchmark:latest .
```
Upload the image to Docker Hub:


```
docker push antonpatsev/sentry-benchmark:latest .
```
Creating Kubernetes Secret:

Replace your-base64-encoded-sentry-dsn with your base64 encoded DSN:


```
echo -n “your-sentry-dsn” | base64 -w0
```
Apply Secret:


```
kubectl apply -f sentry-dsn.yaml
```
Deployment to Kubernetes:

Apply Deployment:


```
kubectl apply -f sentry-benchmark.yaml
```
Notes
Make sure you replace “your-sentry-dsn” with your real DSN.

Replace “your-dockerhub-username” with your real Docker Hub username.

Make sure you have access to your Kubernetes cluster configured and kubectl installed.

This code and instructions will allow you to generate a large number of different exceptions and send them to Sentry for benchmarking, and deploy this process to Kubernetes.
