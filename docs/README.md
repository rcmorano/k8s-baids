`k8sb-init`
-------------

Initializes project's enviroment


`k3s-install`
---------------

Defaults to _k3s-install-systemd_. Please refer to its doc for more info.


`k3s-install-docker-compose`
------------------------------

Install _k3s_ using the official [docker-compose.yml](https://github.com/rancher/k3s/blob/master/docker-compose.yml) and current's dir _.env_ if any.

Examples:

    ```
    k3s-install-docker-compose
    k3s-install-docker-compose --scale node=3
    ```


`k3s-install-systemd`
-----------------------

Install _k3s_ using the the official [install.sh script](https://github.com/rancher/k3s#systemd). To provide any of the supported environment variables, export them before executing this function or in case a _.env_ exists in the current dir, it will be used.

Examples:

    ```
    export INSTALL_K3S_VERSION=vX.Y.Z
    k3s-install-systemd
    ```


`k3s-uninstall`
-----------------

Tries to uninstall 'k3s' using the official uninstall script or bringing down the docker-compose and *all the volumes associated*.


`k8sb-help`
-------------

Returns this documentation in a CLI-friendly format (tomdoc's plain-text).


