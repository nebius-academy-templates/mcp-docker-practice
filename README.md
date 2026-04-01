In this task, you'll package an MCP server into a Docker image, run it in a container, and verify that it works over SSE.

## Workflow at a glance

👩‍💻
1. Set up your environment
2. Complete the `Dockerfile`
3. Build the Docker image
4. Run the container with SSE
5. Verify the health endpoint
6. Submit your task


## 1. Set up your environment

Once you log in to your GitHub account, the repository for this task will be added automatically.

1. Confirm that `mcp-docker-practice` appears in your account. 
2. Clone the repo locally and open it in your editor.
3. Make sure Docker is installed and running.

## 2. Complete the `Dockerfile`

Open `Dockerfile` in the repo root and fill in the TODOs.

Your image should:

- Use `python:3.11-slim` as the base image
- Install `git` (required by GitPython)
- Copy `pyproject.toml` and the source code into the image
- Install the package
- Declare a volume at `/repo`
- Set the default command to start the server

## 3. Build the Docker image

Build the image from the project root:

```
docker build -t git-activity-analyzer .
```

## 4. Run the container with SSE

1. Run the container in SSE mode and expose port 8000 (use the README command).
2. Mount any local Git repo into the container at `/repo`.

## 5. Verify the server is running

Open:

```
http://localhost:8000/health
```

Confirm that the server responds with:

```
{"status":"ok"}
```

## 6. Submit your task

Before submitting, review the submission checklist below.

### ✅ **Submission checklist**

- [ ]  `Dockerfile` is complete with all TODOs filled in
- [ ]  `docker build -t git-activity-analyzer .` succeeds
- [ ]  The container starts and exposes port 8000
- [ ]  `http://localhost:8000/health` returns `{"status":"ok"}`
