# liberate-formula
Formula for SUSE Manager / Uyuni to convert systems from EL clones to SUSE Liberty Linux

Please check [Quickstart](Liberate-Quickstart.md) to learn how to use it

This is the result of the Hackweek 23 project:
https://hackweek.opensuse.org/23/projects/use-uyuni-to-migrate-el-linux-to-sll

# Release a version in OBS
OBS project: https://build.opensuse.org/package/show/home:RDiasMateus:uyuni/liberate-formula

## Version testing status


| OS version  | Status  |
| ----------- | ------- |
| Rhel 9      | Working |
| Rocky 9     | Working |
| Alma 9      | Working |
| Oracle 9    | Working |
| Rhel 8      | Working |
| Rocky 8     | Working |
| Alma 8      | Working |
| Oracle 8    | Working |
| Rhel 7      | Not Tested |
| CentOS 7    | Working |
| Oracle 7    | Working |

# Notes

Analyze if the workaround for EL flavors different from RHEL and CentOS can be removed. Check project https://build.suse.de/package/view_file/SUSE:SLL-9:Import/sll-release/sll-release.spec?expand=1

Salt State & Formula tasks done:
- remove `/usr/share/redhat-release`: DONE
- remove `/etc/dnf/protected.d/redhat-release.conf`: DONE
- install SLL package: DONE
- re-install all packages from SLL channels: DONE 
- add option in Formula and UI to select reinstall: DONE

RPM Build tasks done:
- adapt the version number in the spec file
- add changes entry
- create a local tag and upload it to the repo
- Create a release in git
- download the tar file and save it to the OBS project
- Copy the spec and changes file to the OBS project
- add and commit all to OBS project
