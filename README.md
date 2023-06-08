# rsync-docker

Docker image derived from `alpine`, providing rsync and related tools.

* `git`
* `rsync`
* The `ssh` client (but not the server)
* `ssh-agent`

The image also includes `bash` as its default shell rather than the Alpine-standard `sh`.
This is for the benefit of some GitLab CI configurations, which make use of `bash`
syntax for secret key injection. For an example of this,
see [GitLab-examples/ssh-private-key](https://gitlab.com/gitlab-examples/ssh-private-key).

The provided `build` file builds this image as `iay/rsync` for local use.

Each push to the `main` branch invokes GitHub Actions to build a
multi-architecture image and pushes it to Docker Hub as `ianayoung/rsync:latest`.
