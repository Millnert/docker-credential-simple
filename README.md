# Docker Credential Helper for docker login

A simple credentials helper for docker according to [https://docs.docker.com/engine/reference/commandline/login/#credential-helper-protocol].
It helps you to avoid storing docker registry credentials in source code (it instead must reside on build hosts/containers that need to be
prepared for this).

Put in path and then configure ~/.docker/config.yml to use it:

    {
      "auths": {
        "registry.example.com": {}
      },
      "credHelpers": {
        "registry.example.com": "docker_credhelper.py"
      }
    }

Then perform a `docker login registry.example.com` and enter the credentials, and they should become stored.

You should then be able to use FQDN docker image names such as `docker pull registry.example.com/repo/image:tag`.
