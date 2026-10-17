# Networking Labs | Kavinda Piyumantha

Practical networking study projects focused on Cisco routing, switching, and WAN connectivity.

**Aspiring Network Engineer · ENTC student at the Institute of Technology, University of Moratuwa**

[LinkedIn](https://www.linkedin.com/in/kavinda-piyumantha-641bba407/) · [Email](mailto:kavinda.piyumantha@gmail.com)

## Projects

| Project | Platform | Scope | Current repository status |
|---|---|---|---|
| [Small Office Network](small-office-network/README.md) | Cisco Packet Tracer | VLANs, inter-VLAN routing, DHCP | Configuration templates and build guide available; simulation and testing pending |
| Multi-Site WAN Lab | GNS3 | eBGP to ISP, OSPF over GRE, IPsec, failover | Planned scope; implementation files and test evidence not yet included |

## Start with the office network

1. Read the [topology, addressing plan, and build instructions](small-office-network/README.md).
2. Review the [router configuration](small-office-network/configs/R1.txt) and [switch configuration](small-office-network/configs/SW1.txt).
3. Build the topology in Cisco Packet Tracer and apply the configurations.
4. Complete the validation checklist and save the `.pkt` project.

The baseline allows routing between all departments. ACLs, SSH management, port security, and simulated internet connectivity are planned extensions.

## Multi-Site WAN Lab roadmap

- [ ] Document the site topology and IP addressing plan.
- [ ] Add GNS3 project details and device configurations.
- [ ] Configure and verify eBGP connectivity to the ISP.
- [ ] Configure and verify OSPF over GRE tunnels.
- [ ] Add IPsec encryption and verification outputs.
- [ ] Test link failure and recovery; record observations.

## Documentation and evidence

Each lab should include its objective, topology, addressing table, configurations, build steps, test results, and troubleshooting notes. Completed functionality will be marked only after it is tested and supported by evidence.

## About the author

I am developing practical network engineering skills through hands-on study and documented labs. My focus includes TCP/IP, subnetting, routing, switching, VLANs, and WAN concepts.

A prepared [GitHub profile README](profile/README.md) is also available in this repository.

## License

See [LICENSE](LICENSE).
