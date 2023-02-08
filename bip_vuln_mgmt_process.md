```mermaid
sequenceDiagram
    participant Keith as Keith: Receives monthly Nessus Scan report from ICAMP
    participant Aaron as Aaron: Creates monthly POA&M for Nessus Scan
    participant Aaron as Aaron: Takes Report
    participant Aaron as Aaron: Works on Remediations
    participant Aaron as Aaron: Updates REEF
    participant Aaron as Aaron: Generates new ICAMP report
    participant Aaron as Aaron: Emails both reports to Keith in zip file
    participant Keith as Keith: Uploads zip file to eMASS under RA-5.8
    participant Aaron as Aaron: Uploads zip file to POA&M and closes POA&M
    participant Keith as Keith: Creates POA&M worklfow to close POA&M officially in eMASS

    Keith->Aaron: Emails Nessus Scan report and CC to Ryan
    Aaron->REEF: Takes report and updates REEF
    Aaron->Keith: Emails both reports to Keith in zip file
    Keith->RA-5.8: Uploads zip file to RA-5.8
    Aaron->POA&M: Uploads zip file to POA&M and closes POA&M
    Keith->eMASS: Creates POA&M workflow in eMASS to close POA&M officially
