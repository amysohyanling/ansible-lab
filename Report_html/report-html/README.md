Workflow memos

Pre-checks
  - Gather all facts and keep facts in a stats variable
  - Use the inventory_hostname as part of the variable name
      #FACTS - gather_all_facts_masterv2.yml
        - precheck_facts_result
  
  - Gather all pre-checks results in stats variable 
  - Use the inventory_hostname as part of the variable name
      #STATS - gather_all_facts_masterv2.yml
        - pre_distribution
        - pre_kernel
        - pre_memory
        - pre_host_file
        - pre_resolv_conf
        - pre_mount_point

  - Gather precheck patch list in stats variable
  - Use the inventory_hostname as part of the variable name
      #STATS - pre_patch_masterv2.yml
        - pre_packages_ug

  - Gather running services in stats variable
  - Use the inventory_hostname as part of the variable name
      #STATS - pre_file_masterv2.yml
        - pre_running_services

Snapshot
  - Get snapshot with date & time
  - ss-inventoryv2.yml