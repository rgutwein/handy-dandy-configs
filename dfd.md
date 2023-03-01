```mermaid
graph TD;

  subgraph Application Layer
    A1[Web App 1]
    A2[Web App 2]
    A3[API Gateway]
    A4[API Service 1]
    A5[API Service 2]
    A1 -- HTTPS --> A3
    A2 -- HTTPS --> A3
    A3 -- HTTPS --> A4
    A3 -- HTTPS --> A5
  end

  subgraph Platform Layer
    P1[Ignyte-Cluster]
    P2[Load Balancer]
    P3[Primary postgresql Database]
    P4[Seoncdary postgresql Database]
    P5[Sensitive Encrypted postgresql DB]
    P6[Caching Layer]
    P7[Object Storage]
    P1 -- HTTPS --> P2
    P2 -- HTTPS --> A1
    P2 -- HTTPS --> A2
    P2 -- HTTPS --> A3
    P3 -- HTTPS --> P1
    P4 -- HTTPS --> P1
    P5 -- HTTPS --> P1
    P6 -- HTTPS --> P1
    P7 -- HTTPS --> P1
  end

  subgraph Infrastructure Layer
    I1[Virtual Machines]
    I2[Containers]
    I3[Storage]
    I4[Networking/SDN/SD-WAN]
    I1 -- Hypervisor --> I2
    I2 -- Docker Engine --> P1
    I3 -- iSCSI/NFS --> P3
    I4 -- VPN/VLAN --> P2
  end
