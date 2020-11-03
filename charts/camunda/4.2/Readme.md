# Tecnotree App for DAP Zeebe Broker with embedded gateway

### About:
    This Helm chart is for TT DAP Zeebe Broker with embedded gateway for version Zeebe:0.20.2
  
### Prerequisites:

    - Make sure elastic search URL should be service name for operate
    - Go through the read me for fixes

### Deployment

    Production
    ----------
    Use as the requests and limits as mentioned in the values.yaml
    
    Development / Test
    ------------------
    
    * After answering all questions used edit as Yaml option
      Copy and paste the below section at the end to use lesser resources while deploying.  
    ----------------------
    resources:
      limits:
        cpu: "1000m"
        memory: 4Gi
      requests:
        cpu: "500m"
        memory: 2Gi 
    -----------------------
    * Use the below answer for JAVA_TOOL_OPTIONS
    ------------------------
    -XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap -XX:MaxRAMPercentage=50.0 -Xms2g
    ------------------------
 
### Fixes

    - Enabled Json Logging --> stdout console logs are JSON logs
    - Gateway Time out conf as been configured as question
    - Container Zeebe logs has been mounted on host path where logs can be stored on host with the mentioned path in the question
    - Edited the configmap mount method as per this below link as part of an RCA
      https://kubernetes.io/docs/concepts/storage/volumes/#projected
    - Added time script to show time in UTC, IST and GMT -5 TimeZones
    - Added data folder backup script

### Release Notes:

    - 12 may 2020 12:45:53 PM release 0.2.4.1
    - 19 may 2020 added the following
        - 1. ZEEBE_GATEWAY_REQUEST_TIMEOUT : 2500ms
    - 14 Aug 2020 update the last three fixes    

### Scope:
    - This is copied from folder 4 which is zeebe 0.20.1 version

> Maintained by  : DL-CP-DEVOPS@tecnotree.com



