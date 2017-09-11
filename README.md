============================================ DPM deploy script (draft) =====================================================

I.
To run environment preparation script use command (for example DEV instead of {{ ENV}}):

   ansible-playbook -i inv/{{ ENV }}/hosts prepare.yml

This will prepare env - install Java, WildFly, Nginx on DPM main hosts and PostgreSQL on DPM DB hosts

Number of desired services to start on each DPM main server should be configured in inv/{{ ENV }}/group_vars/services.yml (that could change if we will decide to spread services on different hosts)

II. (TODO)
To run deployment script use command:

   ansible-playbook -i inv/{{ ENV }}/hosts deploy.yml

============================================================================================================================
TO DO:
 1) Deploy role
 2) Investigate if we should do different WildFly installs (different folders on system) rather than use different systemctl services started from one WildFly folder install.
 3) Create Nginx template in dpm_main role.
 4) Extend DB playbook to configure different databases for envs on cluter.
 5) ?
 6) PROFIT!  
