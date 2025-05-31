<p align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/a/af/Tux.png" alt="Linux Logo" width="150"/>


  # Managing Directory and File Permissions in Linux

  ## Platform and Tools Used
  - **Google CyberSecurity labs**
  - **Linux**

  ## Scenario:
In this scenario, we must examine and manage the permissions on the files in the `/home/researcher2/projects` directory for the `researcher2` user.
  
The `researcher2` user is part of the `research_team group`. We must check the permissions for all files in the directory, including any hidden files, to make sure that permissions align with the authorization that should be given. When it doesn't, we must change the permissions.


Here is the task: First, we'll check the user and group permissions for all files in the projects directory. Next, we'll check whether any files have incorrect permissions and change the permissions as needed. Finally, we will check the permissions of the `/home/researcher2/projects/drafts` directory and modify these permissions to remove any unauthorized access.
  
  ___

  ### Task 1. Check file and directory details

  In this task, I explored the permissions of the `projects` directory and the files it contains, including hidden files.

1. Used the `ls` command to list the contents of the current directory. The output confirmed the presence of the `projects` directory.

2. Navigated to the `projects` directory using the command `cd projects`.

3. Ran `ls -la` to review the permissions of all files in the `projects` directory, including hidden files.
   
   ![Screenshot 2025-05-28 200018](https://github.com/user-attachments/assets/47ec596d-775c-4c07-8b5d-b1889cd3be1c)


 ### Task 2. Change file permissions

  The organization decided that "**other**" users should not have write access to any of their files. To comply with this policy, I reviewed the previously returned file permissions and identified that `project_k.txt` had write access for **other**. I then removed this permission from **other** users to ensure compliance.

1. Ran the command `chmod o-w project_k.txt` to remove the **write** permission for **other** users from `project_k.txt` file.

2. Used the `ls -l` command to list the files again and verify that the **write** permission was removed — which it confirmed.
  
  ![Screenshot 2025-05-28 202502](https://github.com/user-attachments/assets/80a79ff4-7dbd-4625-bc9e-88b379ce331b)



  ### Task 3. Change file permissions on a hidden file
  
My organization recently archived `.project_x.txt`. They do not want anyone to have write access to this file, but the user and group should have read access. 

I reviewed the permissions of the `.project_x.txt` file and found that both the **user** and **group** had **write** access, while only the **user** had **read** access. To comply with policy, my task is to remove **write** privileges from both the **user** and **group**, and grant **read** permission to the **group**.

1. Used the command `ls -la .project_x.txt` to display the current file permissions.

2. Ran the command `chmod u-w,g-w,g+r .project_x.txt` to remove **write** access for the **user** and **group**, and to grant **read** access to the **group**.

3. Used `ls -la .project_x.txt` again to verify that the changes were applied. The output confirmed the permissions were updated correctly.

![Screenshot 2025-05-28 203600](https://github.com/user-attachments/assets/5b3b7538-dc04-4a16-88d8-623d44ee5d40)

  ### Task 4. Change directory permissions

  My organization requires that only the `researcher2` 'user' have access to the drafts directory and its contents. To enforce this, execute permissions should be restricted exclusively to `researcher2`, with no access granted to others.

I reviewed the permissions of the `draft` directory and found that **group** still had execute access, which should be limited to the user only. To comply with policy, my task is to remove execute permission from the **group** and ensure that only the user retains that privilege.

1. Ran the `ls -l` command to display the file permissions and identified that the **group** on `drafts` directory still had **execute** permission, which needed to be removed.

2. Used the command `chmod g-x drafts` to remove **execute** permission from the **group**.

3. Ran `ls -l` again to verify that the changes were applied. The output confirmed that the permissions were updated correctly.
   
 ![Screenshot 2025-05-28 204443](https://github.com/user-attachments/assets/d7b5ee2a-74f4-4e1e-ad24-d451e1d8a236)


_____
  ## Conclusion

  I modified several file and directory permissions within the `projects` directory to align with my organization's access control requirements. I began by running `ls -la` to review the current permission settings, which guided my next steps. Based on this information, I used the `chmod` command multiple times to adjust permissions as needed.



  

  
