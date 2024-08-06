Workflow memos

Pre-checks
  - Gather all facts and keep facts in a stats variable
  - Use the inventory_hostname as part of the variable name
      #FACTS - gather_all_facts_masterv2.yml
        - precheck_facts_result
  
  - Gather all pre-checks results in stats variable 
  - Use the inventory_hostname as part of the variable name
      - STATS - gather_all_facts_masterv2.yml
        - pre_distribution
        - pre_kernel
        - pre_memory
        - pre_host_file
        - pre_resolv_conf
        - pre_mount_point

  - Gather precheck patch list in stats variable for pre
  - Use the inventory_hostname as part of the variable name
      - STATS - pre_patch_masterv2.yml
        - pre_packages_ug

  - Gather running services in stats variable
  - Use the inventory_hostname as part of the variable name
      - STATS - pre_file_masterv2.yml
        - pre_running_services

Snapshot
  - Get snapshot with date & time
  - ss-inventoryv2.yml


Update
  - Update
  - Gather the history of upgrade in stats variable
  - Use the inventory_hostname as part of the variable name
  - map the updates and only select the defined part
  - patch_masterv2.yml


Postcheck
  - Gather precheck patch list in stats variable for post
  - Use the inventory_hostname as part of the variable name
      - STATS - pre_patch_masterv2.yml
        - post_packages_ug
  
  - Gather yum history info in stats variable
  - Use the inventory_hostname as part of the variable name
      - STATS - post_patch_result_masterv2.yml
        - yum_update_history_result

  - Gather running services in stats variable
  - Use the inventory_hostname as part of the variable name
      - STATS - post_file_masterv2.yml
        - post_running_services
    
  - Gather all facts and keep facts in a stats variable
  - Use the inventory_hostname as part of the variable name
      - FACTS - post_file_masterv2.yml
        - postcheck_facts_result
  
  - Gather all pre-checks results in stats variable 
  - Use the inventory_hostname as part of the variable name
      - STATS - post_file_masterv2.yml
        - post_distribution
        - post_kernel
        - post_memory
        - post_host_file
        - post_resolv_conf
        - post_mount_point

Generate Report

  - Consolidate the entire report into one using run_once
  - Gather the system information (for host in inventory_hostname)

    - hostname
    - ip address

  - Gather the before and after for precheck abd postcheck
  - input the column mark as changes or no changes
    - this includes all the prechecks and postchecks files data
  
  - Gather the packages that are updated
  - only list out the updated packages

  - Gather the difference in the running services
  - compare the running services for pre running and post running services