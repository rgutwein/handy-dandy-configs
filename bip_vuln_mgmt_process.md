```mermaid
sequenceDiagram
    Keith Fuhrman->Aaron Douglas: Emails Nessus Scan report and CC to Ryan
    Aaron Douglas->REEF: Takes report and updates REEF
    Aaron Douglas->Keith Fuhrman: Emails both reports to Keith in zip file
    Keith Fuhrman->RA-5.8: Uploads zip file to RA-5.8
    Aaron Douglas->POA&M: Uploads zip file to POA&M and closes POA&M
    Keith Fuhrman->eMASS: Creates POA&M workflow in eMASS to close POA&M officially
