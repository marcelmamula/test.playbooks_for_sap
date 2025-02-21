# Ansible Playbook - SAP S/4HANA Sandbox installation

This Ansible Playbook can be executed with:
- Ansible to provision hosts
- Ansible + Terraform to provision hosts
- Existing hosts

This Ansible Playbook can be targeted at the following Infrastructure Platforms:
- Amazon Web Services (AWS)
- Google Cloud Platform (GCP)
- IBM Cloud
- IBM Cloud, IBM Power Virtual Servers
- Microsoft Azure (MS Azure)
- IBM PowerVM
- OVirt
- VMware

SAP S/4HANA installation:
- Sandbox System definition by SAP: all SAP HANA and SAP NetWeaver instances run on a single host.
- System Topology/Architecture: a Sandbox System is commonly referred as Two-Tier Architecture, may also be known as OneHost or Central System.

SAP S/4HANA software versions:
2023, 2022, 2021, 2020, 1909

---

## Execution of Ansible Playbook

Prior to execution, please read the [full documentation of the Ansible Playbooks for SAP](../../docs/README.md) for the capabilities and different execution methods.

## Execution outcome

When executing this Ansible Playbook for SAP, the following hosts are provisioned (unless an Ansible Inventory is provided for existing hosts):
1. Host for SAP HANA Database Server and SAP NetWeaver Application Server (ABAP) - Central Services (ASCS) and Primary Application Server (PAS)

The sequence of a Standard System installation is:
- `hdblcm`: Install SAP HANA database server
- `SWPM`: Install SAP NetWeaver Application Server (ABAP) and Installation Export to Database (i.e. Database Load)

This therefore matches to the SAP SWPM Product ID prefixes that are executed in sequence:
- `NW_ABAP_OneHost`, Central Services, Database Instance Installation, Primary Application Server
