ocp-cro-e2e: OCP Cluster Resource Override admission operator e2e Test Cases
=========

This module will run end to end test cases. Results will be stored in ~/cro_e2e_output.txt/ file on bastion.

Requirements
------------

 - Running OCP 4.x cluster is needed.

Role Variables
--------------

| Variable                    | Required | Default                                    | Comments                                            |
|-----------------------------|----------|--------------------------------------------|-----------------------------------------------------|
| cro_podman_password         | no       | "https://github.com/openshift/origin"        | Git repo url for the e2e tests                      |
| cro_podman_username         | no       | https://github.com/openshift/origin        | Git repo url for the e2e tests                      |
| cro_git_repo                | no       | ""                                         | URL to list of testcases to be excluded             |
| cro_catalogsource           | no       | /tmp/openshift_ws                          | Test directory                                      |
| cro_catalogsource_image     | no       | ""                                         | The cluster will be upgraded to this image by e2e. In case of an empty string, the upgrade won't be done. |
| cro_golang_tarball          | no       | https://dl.google.com/go/go1.20.linux-ppc64le.tar.gz | HTTP URL for golang tarball             |
| cro_enabled                 | no       | false                                      | Flag to be set to true to enable e2e tests playbook |

Dependencies
------------

 - None

Example Playbook
----------------

    - name: Run cro e2e test cases
      hosts: bastion
      roles:
      - ocp-cro-operator

License
-------

See LICENCE.txt

Author Information
------------------

Prajyot Parab (prajyot.parab@ibm.com)
