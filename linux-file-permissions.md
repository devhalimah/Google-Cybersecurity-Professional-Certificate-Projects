<h2>Scenario</h2>
<p>
  You are a security professional at a large organization. You mainly work with their research team. Part of your job is to ensure users on this team are authorized with the appropriate permissions. This helps keep the system secure.</p>

<p>Your task is to examine existing permissions on the file system. You’ll need to determine if the permissions match the authorization that should be given. If they do not match, you’ll need to modify the permissions to authorize the appropriate users and remove any unauthorized access.</p>


<h3>Solution</h3>
<b>Step 1 (Checking file and directory details):</b>
<p>
  Important commands used to check file and directory details are:
  <ul>
    <li><pre>ls command - Used to display all files and sub-directories in a directory</pre></li>
    <li><pre>ls -l command - To list the contents and permissions of the directory</pre></li>
    <li><pre>ls -a command - To find hidden files in the directory</pre></li>
  </ul>
  The combination of commands (2) and (3) above <i>(i.e. ls -al)</i> will list the contents and permissions of hidden files in the directory.
  <img width="960" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/ea159845-c01d-43aa-b40c-850fe03a2f86">
</p>

<b>Step 2 (Description of the permissions string above):</b>
<p>
   The 10-character string (rwxrwxrwx) above represents read, write, execute permissions for users, groups, and other users in the filesystem.<br>The permissions string looks like this for directories(d): <pre>drwxrwxrwx</pre> and is represented by this for regular files(-): <pre>-rwxrwxrwx</pre>.
</p>

<b>Step 3 (Changing file permissions):</b>
<p>
  The organization does not allow other to have write access to any files. As a system administrator following the principle of least privilege, I checked files with incorrect permissions and changed the permissions as needed.<br>
  <img width="960" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/14056d1d-5909-4715-a393-8d67a31469d3">
<u>
  <li>The file "project_k.txt" has write permissions for others which is against the organization's policy. To remove the write command, I entered the command below:
    <pre>chmod o-w project_k.txt</pre></li>
  <li>Furthermore, the file "project_m.txt" is a restricted file and should not be readable or writable, even by the group. I entered the command below to change the permissions of the project_m.txt file so that the group doesn’t have read permissions.
    <pre>chmod g-r project_m.txt</pre></li>
  </u>
</p>

<b>Step 4 (Changing file permissions on a hidden file):</b>
<p>
  Since the research team has archived .project_x.txt, it is why it’s a hidden file and should not have write permissions for anyone, but the user and group should be able to read the file.<br> To assign the appropriate authorization for this file as the system administrator, I entered the command below:
  <pre>chmod u-w,g-w,g+r .project_x.txt</pre>
  <img width="960" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/6198d42e-1ab2-4a3e-a9ca-20ee7873dca0">
  <br>This will restrict unauthorized access and strengthen security on the system.
</p>

<b>Step 5 (Changing directory permissions):</b>
<p>
  <img width="960" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/92bc763f-0053-48f8-b24a-0e62f689f305">
  <br>The files and directories in the projects directory belong to the researcher2 user. So, only this user is meant to have access to the drafts directory and its contents.<br> As a Linux system administrator, I used the command below to modify the permissions accordingly:
  <pre>chmod g-x drafts</pre>
  This command removes execute permission for group, allowing only researcher2 user to have access to the drafts directory and its contents.
</p>

<b>Summary:</b>
<p>
 As a Linux system administrator and cybersecurity professional, I have successfully examined existing permissions on the organization's file system, modified the permissions to authorize appropriate users and removed all unauthorized access. This implementation of least privilege principle has further strengthened the organization's security system and posture.
</p>
