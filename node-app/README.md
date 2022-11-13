# Assignment solution

This exercise doesn't differ to much from [python app](../python-app/README.md).

The only thing to take into account is that the dockerized application is
actually a web server, so, either you run it in detach mode (`-d` option) or
not, you have to stop the container before remove it, and don't forget to
"expose" the port using the `-p <local-port>:3000` option.
