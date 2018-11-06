# EMBL-EBI Cloud Portal - api test

This application uses Terraform for deploying the official iso CentOS 7.4 image and configures a Redis server using a Galaxy Ansible role. Other iso image is also supported specifying a different `disk_image_name`. When using a Ubuntu or other OS, you need also to configure the `remote_user` parameter according to it (`ubuntu` in this case).

___

## Requirements
A network is expected to be shared with other virtual machines, therefore is not provided and destroyed with this terraform description.
You need to set up the name of the network inside of the terraform.tfvars file.
If you want to provide a new network you can use the cpa-network terraform description.

## Instructions
Create a new entry in the `Deployment Parameters` section.

The only required input is the instance_number, which is the Number of instances to deploy.

#This application can be used in combination with one of the following :

#[https://github.com/EMBL-EBI-TSI/](https://github.com/EMBL-EBI-TSI/)

## Default values

### `Deployment parameters`
| Parameter name          | Parameter value                 |
| ---                     | ---                             |
| `name`                  | `apitest`                |
| `redis_version`    | `3.0.7` |
| `parameter_2_name`   | `parameter_2_default_value`|
|                         |                                 |
| `disk_image_name`       | `centos-7.4`                    |
| `remote_user`           | `centos`                        |
| `machine_type`          | `s1.tiny`                       |
| `floating_ip_pool`      | `ext-net`                       |
| `network_name`          | ``                              |
| `ssh_key`               | ``                              |
| `public_key_path`       | `~/.ssh/id_rsa.pub`             |
| `private_key_path`      | `~/.ssh/id_rsa`                 |
| `user_private_key_path` | `~/.ssh/id_rsa`                 |

### `Inputs`
| Input name              | Input value                     |
| ---                     | ---                             |
| `instance_number`      | `1`             |
| `redis_bind`     | `None`            |


### Open Ports
The virtual machine provided will have this ports open.

-   `ICMP`: `all`
-   `TCP` : `22`
-   `redis`:``6379``

### Ansible roles
Ansible Galaxy:
[https://galaxy.ansible.com/davidwittman/redis](https://galaxy.ansible.com/davidwittman/redis)

## :shipit:
<sub>This is  an application for the [EMBL-EBI Cloud Portal](https://portal.tsi.ebi.ac.uk) , generate using:
[https://github.com/EMBL-EBI-TSI/cpa-template](https://github.com/EMBL-EBI-TSI/cpa-template)</sub>