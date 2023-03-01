```mermaid
flowchart LR
subgraph "AWS GovCloud"
    subgraph "FedRAMP Authorization Boundary"
        subgraph "Ignyte_Cluster"
            subgraph "Containerized Applications"
                subgraph "Application Data"
                    A[Reporting and Analytics Data]
                end
            end
            subgraph "Ignyte-Platform (CM-6)"
                C[Primary postgresql DB]
                D[Seoncdary postgresql DB]
                E[Sensitive Encrypted Postgresql DB]
                F[docker]
            end
        end
        subgraph "Infrastructure"
            subgraph "AWS Services (CM-6)"
                G[EC2]
                H[VPC]
                I[S3]
                J[RDS]
            end
            subgraph "LDAP Configuration (AC-2)"
                K[OpenLDAP]
            end
        end
    end
    subgraph "NIST 800-53 Controls"
        subgraph "Access Controls (AC-2)"
            K
        end
        subgraph "Configuration Management (CM-6)"
            C
            D
            E
            F
            G
            H
            I
            J
            K
        end
        subgraph "Cryptographic Protection (SC-13)"
            G
            H
            A
        end
        subgraph "Flaw Remediation (SI-2)"
            A
        end
        subgraph "Vulnerability Scanning (RA-5)"
            A
        end
        subgraph "Continuous Monitoring (CA-7)"
            J
            C
            D
            E
            F
            G
            H
            I
            A
        end
        subgraph "Information System Monitoring (SI-4)"
            A
        end
    end
end

