# image-management

There are 4 steps and corresponding 4 jenkins pipeline, given below:

1. imageManagement - Create patched and hardened image on AWS along with versioning and tagging of linux and windows (in progress) both
2. scanImage - It identifies all AMIs on the basis of particular tags and scan all AMIs one by one using lynis and rkhunter and send report via email. It provides 2 reports (lynis report and rootkit report) and email those
3. distributeImage - It is parameterized job with 3 parameters Operation_Type: Add/Remove (grant/revoke instance creation permission from shared AMI), Account_ID and AMI_ID. It shares or remove all provided AMIs to/from given AWS account
4. decommissionAMI - It decommission AMIs from the parameter list from the Master AWS account
