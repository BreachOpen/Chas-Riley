<div style="display: inline-block;">
  <a href="https://breachopen.github.io/Chas-Riley/">
    <img src="https://img.shields.io/badge/Home-3ba0e6" alt="Home">
  </a>
</div>

<div style="display: inline-block;">
  <a href="https://github.com/BreachOpen/Chas-Riley/" target="_blank">
    <img src="https://img.shields.io/badge/Github_Source-3ba0e6" alt="Github Source">
  </a>
</div>

---

# Managing Authorization/File permissions in Linux

## Scenario
You are a security professional at a large organization. You mainly work with their research team. Part of your job is to ensure users on this team are authorized with the appropriate permissions. This helps keep the system secure. Your task is to examine existing permissions on the file system. You’ll need to determine if the permissions match the authorization that should be given. If they do not match, you’ll need to modify the permissions to authorize the appropriate users and remove any unauthorized access.<br /><br />

## Tasks Given
1: **Check file and directory details**<br />
- Navigate to the projects directory.
- List the contents and permissions of the projects directory.<br />

![Directory Details](../../assets/img/network/permission/1.png)

<br />
- Check whether any hidden files exist in the projects directory.<br />

![Hidden Files](../../assets/img/network/permission/2.png)

<br />
2: **Change file permissions**<br />
- Check whether any files in the projects directory have write permissions for the owner type of other.<br />
- Change the permissions of the file identified in the previous step so that the owner type of other doesn’t have write permissions.<br />

![project_k.txt](../../assets/img/network/permission/3.png)

<br />
- The file project_m.txt is a restricted file and should not be readable or writable by the group or other; only the user should have these permissions on this file. List the contents and permissions of the current directory and check if the group has read or write permissions.<br />
- Use the chmod command to change permissions of the project_m.txt file so that the group doesn’t have read or write permissions.<br />

![project_m.txt](../../assets/img/network/permission/4.png)

<br />
3: **Change file permissions on a hidden file**<br />
- Check the permissions of the hidden file .project_x.txt and answer the question that follows.<br />
- Change the permissions of the file .project_x.txt so that both the user and the group can read, but not write to, the file.<br />

 ![.project_x.txt](../../assets/img/network/permission/5.png)

<br />
4: **Change directory permissions**<br />
- Check the permissions of the drafts directory and answer the following question.<br />
- Remove the execute permission for the group from the drafts directory.<br />

![drafts directory](../../assets/img/network/permission/6.png)

<br />
5: **Conclusion**<br />
After a few hours of practice and then this practical application scenario using a Linux Bash shell, I was able to;
- Examine file and directory permissions
- Change permissions on files
- Change permissions on directories

--- 
