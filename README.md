<h1 align="center">Project: Using Linux Commands to Manage File Permissions</h1>

<p>This project, led by the Google Cyber Security Course, demonstrates how to enforce the "Least Privilege" security principle by managing file permissions on a Linux platform.</p>

<h2>Project Overview</h2>

<h3>Scenario</h3>
<p>As an IT professional within a major finance organization, I led a project focused on enforcing the "Least Privilege" security principle through precise management of file permissions on the Linux platform. The core of this initiative was the strategic adjustment of user, group, and other permissions within the <code>/home/researcher2/projects</code> directory, a critical area accessed by the <code>researcher2</code> user and associated with the <code>research_team</code> group.</p>

<h3>Key Actions</h3>
<ul>
  <li><strong>Permission Audit:</strong> Conducted a comprehensive review of all file permissions in the target directory, including hidden files, to identify and rectify any deviations from required security protocols.</li>
  <li><strong>Permission Adjustment:</strong> Implemented targeted modifications to permissions that did not align with the minimal necessary access levels, utilizing Linux CLI tools for precise and effective changes.</li>
</ul>

<h3>Objective</h3>
<p>The project aimed to bolster data security by ensuring strict adherence to the "Least Privilege" principle, minimizing potential vulnerabilities while maintaining operational functionality.</p>

<h2>Steps</h2>

<h3>Step 1 - Check File and Directory Details</h3>
<p>My first step is to check the file and directory details within the <code>projects</code> directory. To display all permissions, including hidden files, I use the <code>ls -la</code> command.</p>

<p align="center" style="margin-top: 10px;">
  <img src="https://github.com/user-attachments/assets/1925a64a-3412-4bc8-9fbf-a31b1709e46c" alt="Image Description" width="900"/>
</p>

<h3>Step 2 - Describe the Permissions String</h3>
<p>After using the <code>ls -la</code> command, I can see all permissions for directories and files, including hidden ones. By examining the <code>drafts</code> directory, I observe that the user has read, write, and execute permissions, the group has execute permissions, and others have no permissions. (Permissions string: <code>drwx--x---</code>).</p>

<p align="center" style="margin-top: 10px;">
  <img src="https://github.com/user-attachments/assets/b8cf4c73-8399-4809-9396-118515797961" alt="Image Description" width="900"/>
</p>

<h3>Step 3 - Change File Permissions</h3>
<p>The organization’s policy requires that others do not have write access to any files. I identify <code>project_k.txt</code> as the only file where others have write access, so I use <code>chmod o-w project_k.txt</code> to remove that permission. I then confirm the change with <code>ls -la</code>.</p>

<p align="center" style="margin-top: 10px;">
  <img src="https://github.com/user-attachments/assets/e4993fed-cc73-4fa3-a97c-4af1dd13c368" alt="Image Description" width="900"/>
</p>

<p>Additionally, the organization prohibits group members from reading the file <code>project_m.txt</code>. I remove this permission using <code>chmod g-r project_m.txt</code> and confirm the change with <code>ls -la</code>.</p>

<p align="center" style="margin-top: 10px;">
  <img src="https://github.com/user-attachments/assets/244eb88b-dc5c-457d-85bf-4be9476fe95c" alt="Image Description" width="900"/>
</p>

<h3>Step 4 - Change File Permissions on a Hidden File</h3>
<p>Using the <code>ls -la</code> command, I identify a hidden file, <code>.project_x.txt</code>. Both the user and group have write permissions, which is against policy. I remove these permissions with <code>chmod u-w,g-w .project_x.txt</code>.</p>

<p align="center" style="margin-top: 10px;">
  <img src="https://github.com/user-attachments/assets/be5f5ef9-cbd0-4744-a139-4601e5ec8d26" alt="Image Description" width="900"/>
</p>


<h3>Step 5 - Change Directory Permissions</h3>
<p>In this final step, I ensure that only the <code>researcher2</code> user has access to the <code>drafts</code> directory.</p>

<p align="center" style="margin-top: 10px;">
  <img src="https://github.com/user-attachments/assets/17907dc6-1a30-41db-9f73-661759b1e4f6" alt="Image Description" width="900"/>
</p>

<p>Checking the directory permissions with <code>ls -l</code>, I see that the group has execute permissions on files within this directory. To align with policy, I use <code>chmod g-x drafts</code> to remove the execute permission for the group, and confirm the change with <code>ls -l</code>.</p>

<p align="center" style="margin-top: 10px;">
  <img src="https://github.com/user-attachments/assets/7650744d-c124-4e10-8c38-cd01930108c7" alt="Image Description" width="900"/>
</p>

<h2>Summary</h2>
<p>In this project, as an IT professional for a large finance organization, I undertook the responsibility of enforcing the principle of "Least Privilege" by managing file and directory permissions within the Linux Command Line Interface (CLI). The focus was on the <code>/home/researcher2/projects</code> directory, belonging to the user <code>researcher2</code>, who is a member of the <code>research_team</code> group.</p>
<p>The process began with an examination of all files and directories, including hidden ones, within the specified directory. This was achieved by employing the <code>ls -la</code> command to display detailed permissions for each item.</p>
<p>Upon review, it was noted that certain permissions did not align with the organization's security policy. Specifically:</p>
<ul>
  <li>A file named <code>project_k.txt</code> was improperly granting write access to others. This was rectified by executing the <code>chmod o-w project_k.txt</code> command, thereby revoking the write permission for others.</li>
  <li>The file <code>project_m.txt</code> was accessible by the group, contrary to policy requirements. The read privilege for the group was removed using <code>chmod g-r project_m.txt</code>.</li>
  <li>A hidden file, <code>.project_x.txt</code>, had write permissions for both the user and the group, which was against the desired security posture. These permissions were removed with <code>chmod u-w,g-w .project_x.txt</code>.</li>
  <li>The <code>drafts</code> directory required adjustments to ensure that only the <code>researcher2</code> user could access its contents. The execute permission for the group was removed with <code>chmod g-x drafts</code>, aligning the directory's access permissions with the principle of "Least Privilege."</li>
</ul>
<p>Each modification was verified with subsequent <code>ls -la</code> or <code>ls -l</code> commands to confirm that the changes were successfully implemented.</p>
<p>This project showcases not only my application of critical security principles within a Linux environment but also demonstrates my proficiency in using command-line tools to manage and secure file and directory permissions effectively.</p>
