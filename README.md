<p align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/a/af/Tux.png" alt="Linux Logo" width="150"/>


  # Managing Directory and File Permissions in Linux

  ## Platform and Tools Used

  ## Scenario:
  In this scenario, you must examine and manage the permissions on the files in the `/home/researcher2/projects` directory for the `researcher2` user.
  
The `researcher2` user is part of the `research_team group`.
You must check the permissions for all files in the directory, including any hidden files, to make sure that permissions align with the authorization that should be given. When it doesn't, you must change the permissions.

Here’s how you’ll do this task: First, you’ll check the user and group permissions for all files in the projects directory. Next, you’ll check whether any files have incorrect permissions and change the permissions as needed. Finally, you’ll check the permissions of the `/home/researcher2/projects/drafts` directory and modify these permissions to remove any unauthorized access.
  
  ___

  ### Task 1. Check file and directory details

  In this task, I explored the permissions of the projects directory and the files it contains, including hidden files:

1. Used the `ls` command to list the contents of the current directory. The output confirmed the presence of the `projects` directory.

2. Navigated into the `projects` directory using the command `cd projects`.

3. Ran `ls -la` to review the permissions of all files in the directory, including hidden files.
   
   ![Screenshot 2025-05-28 200018](https://github.com/user-attachments/assets/47ec596d-775c-4c07-8b5d-b1889cd3be1c)
_____

 ### Task 2. Change file permissions

  The organization decided that "**other**" users should not have write access to any of their files. To comply with this policy, I reviewed the previously returned file permissions and identified that `project_k.txt` had write access for **other**. I then removed this permission to ensure compliance.
  


  ### Task 3. Change file permissions on a hidden file
  
The research team at my organization recently archived `project_x.txt`. They do not want anyone to have write access to this file, but the user and group should have read access. 


  ### Task 4. Change directory permissions

  My organization requires that only the `researcher2` user have access to the drafts directory and its contents. To enforce this, execute permissions should be restricted exclusively to `researcher2`, with no access granted to others.


_____
  ## Conclusion



  

  
