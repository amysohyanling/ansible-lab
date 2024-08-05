Workflow memos

Pre-checks
  - Gather all facts and keep facts in a stats variable
  - Use the inventory_hostname as part of the variable name
      -
  
  - Gather all pre-checks results in sats variable 
  - Use the inventory_hostname as part of the variable name
      #STATS
        - pre_distribution
        - pre_kernel
        - pre_memory
        - pre_host_file
        - pre_resolv_conf
        - pre_mount_point
