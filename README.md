<!-- note marker start -->
NOTE: This repo contains only the documentation for the private BoltsOps repo code.
Original file: https://github.com/boltops-pro/terraform-google-network/blob/master/README.md
The docs are publish so they are available for interested subscribers.
For access to the source code, you can become a BoltOps subscriber.
See: https://learn.boltops.com

<!-- note marker end -->

## Network Layer

Configure tfvars for the network stack.

    app/stacks/network/tfvars
    ├── dev.tfvars
    └── prod.tfvars

To deploy the network stack:

    TS_ENV=dev  terraspace up network
    TS_ENV=prod terraspace up network

This creates the vpc with subnets for app, data, proxy tiers.  Secondary ranges are created for for GKE networking. A Cloud NAT and Router is also created to allow VMs without external IPs to communicate to the internet.  The VPC looks something like this:

![](https://img.boltops.com/images/modules/vpc/vpc.png)

