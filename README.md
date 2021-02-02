# DOCUMENTATION  Run STCv traffic generator instances with public and test networks. Instances can be controlled by the Spirent TestCenter application.  <!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK --> ## Requirements
## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.13.0 |
| azurerm | >=2.37.0 |

## Providers

| Name | Version |
|------|---------|
| azurerm | >=2.37.0 |
| null | n/a |
| template | n/a |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| admin\_email | Cluster admin user email. Use this to login to instance web page.  Default is obtained from AION user information. | `string` | `""` | no |
| admin\_first\_name | Cluster admin user first name. Default is obtained from AION user information. | `string` | `""` | no |
| admin\_last\_name | Cluster admin user last name.  Default is obtained from AION user information. | `string` | `""` | no |
| admin\_password | Cluster admin user password. Use this to login to to the instance web page. | `string` | n/a | yes |
| admin\_username | Administrator user name. | `string` | n/a | yes |
| aion\_image\_name | AION image created from private vhd file | `string` | n/a | yes |
| aion\_password | AION user password for aion\_url | `string` | n/a | yes |
| aion\_url | AION URL | `string` | n/a | yes |
| aion\_user | AION user registered on aion\_url | `string` | n/a | yes |
| cluster\_names | Instance cluster names.  List length must equal instance\_count. | `list(string)` | `[]` | no |
| dest\_dir | Destination directory on the instance where provisining files will be copied | `string` | `"~"` | no |
| enable\_provisioner | Enable provisioning | `bool` | `true` | no |
| http\_enabled | Allow HTTP access as well as HTTPS.  Normally this is not recommended. | `bool` | `false` | no |
| ingress\_cidr\_blocks | List of management interface ingress IPv4/IPv6 CIDR ranges. | `list(string)` | <pre>[<br>  "0.0.0.0/0"<br>]</pre> | no |
| instance\_count | Number of instances to create. | `number` | `1` | no |
| instance\_name | Name assigned to the AION instance.  An instance number will be appended to the name. | `string` | `"aion"` | no |
| instance\_size | The Azure Virtual Machine SKU. | `string` | n/a | yes |
| local\_admin\_password | Cluster local admin password for instance SSH access.  Will use admin\_password if not specified. | `string` | `""` | no |
| metrics\_opt\_out | Opt-out of Spirent metrics data collection | `bool` | `false` | no |
| mgmt\_plane\_subnet\_id | Management public Azure subnet ID. | `string` | `""` | no |
| node\_names | Instance cluster node names.  List length must equal instance\_count. | `list(string)` | `[]` | no |
| node\_storage\_provider | Cluster node storage provider | `string` | `"local"` | no |
| node\_storage\_remote\_uri | Cluster node storage URI.  Leave blank for default when provider is local | `string` | `""` | no |
| private\_key\_file | File path to private key | `string` | n/a | yes |
| public\_key | File path to public key. | `string` | n/a | yes |
| resource\_group\_location | RG location in Azure | `string` | `""` | no |
| resource\_group\_name | RG name in Azure | `string` | `""` | no |
| virtual\_network\_name | VNET name in Azure | `string` | `""` | no |

## Outputs

| Name | Description |
|------|-------------|
| instance\_ids | List of instance IDs |
| instance\_private\_ips | List of private IP addresses assigned to the instances, if applicable |
| instance\_public\_ips | List of public IP addresses assigned to the instances, if applicable |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
