# Docker Credential Helper for docker login

A simple credentials helper for docker according to [https://docs.docker.com/engine/reference/commandline/login/#credential-helper-protocol]

Put in path and then configure ~/.docker/config.yml to use it:

    {
      "auths": {
	"registry.example.com": {}
      },
      "credHelpers": {
        "registry.example.com": "docker_credhelper.py"
      }
    }

You should then be able to use FQDN docker image names such as `docker pull registry.example.com/repo/image:tag`.
