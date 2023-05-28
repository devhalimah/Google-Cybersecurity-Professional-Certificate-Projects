<h2>Scenario</h2>
<p>You are a security professional at a large organization. Part of your job is to investigate security issues to help keep the system secure. You recently discovered some potential security issues that involve login attempts and employee machines.</p>

<p>Your task is to examine the organization’s data in their <b>employees</b> and <b>log_in_attempts</b> tables. You’ll need to use SQL filters to retrieve records from different datasets and investigate the potential security issues.</p>

<h3>Solution</h3>
<b>Step 1 (Retrieving after-hours failed login attempts):</b><br>
   The organization database contains the following tables: <u list-style-type="none"><li>log_in_attempts</i> <li>employees</i></u>
   <p>
   <pre>The <b>'log_in_attempts'</b> table has the following columns</pre>
    <ul>
    <li><b>event_id:</b> The identification number assigned to each login event.</li>
    <li><b>username:</b> The username of the employee.</li>
    <li><b>login_date:</b> The date the login attempt was recorded.</li>
    <li><b>login_time:</b> The time the login attempt was recorded.</li>
    <li><b>country:</b> The country where the login attempt occurred.</li>
    <li><b>ip_address:</b> The IP address of that employee’s machine.</li>
    <li><b>success:</b> The success of the login attempt; FALSE (0) indicates a failed attempt.</li>
    </ul>

The time of the login attempt is found in the <b>login_time</b> column. The <b><i>success</i></b> column contains a value of 0 when a login attempt failed and 1 when it is successful.
</p>
<p>
   <pre>The <b>'employees'</b> table has the following columns</pre>
    <ul>
      <li><b>employee_id:</b> The identification number assigned to each employee.</li>
      <li><b>device_id:</b> The identification number assigned to each device used by the employee.</li>
      <li><b>username:</b> The username of the employee.</li>
      <li><b>department:</b> The department the employee is in.</li>
      <li><b>office:</b> The office the employee is located in.</li>
    </ul>
</p>
<p>
 We'll assume that like most large organizations, this organizations's closing time is 18:00. So I'll use the following SQL filters to create a query that identifies all failed login attempts that occurred after 18:00:
<ul>
  <li>WHERE</li>
  <li>AND</li>
</ul><p>
<img width="960" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/38fb488f-321e-4edc-948b-6579bc03666f">
</p>
</p>

-------------------------------------------------------------------------------------------------------------------------
<b>Step 2 (Retrieving login attempts on specific dates):</b>
<h4>Sub-Scenario</h4> 
<p>A suspicious event occurred on 2022-05-09. To investigate this event, we'll have to review all login attempts which occurred on this day and the day before.<br>
The date of the login attempt is found in the <b>login_date column</b>.<br>
So I'll use the following SQL filters to create a query that identifies all login attempts that occurred on 2022-05-09 or 2022-05-08:
<ul>
  <li>WHERE</li>
  <li>OR</li>
</ul><p>
<img width="960" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/c7083ea7-a423-4a99-be0d-225672fb80a0">
</p>
</p>

----------------------------------------------------------------------------------------------------------------------------
<b>Step 3 (Retrieving login attempts outside of Mexico):</b>
<h4>Sub-Scenario</h4> 
<p>There have been suspicious activity with login attempts, but the team has determined that this activity didn't originate in Mexico. Now, we need to investigate login attempts that occurred outside of Mexico (i.e. checking country values of both MEX and MEXICO).<br>
I will use the following SQL filters to create a query that identifies all login attempts that occurred outside of Mexico:
<ul>
  <li>WHERE</li>
  <li>NOT</li>
  <li>LIKE</li>
  <li>A wildcard(%) to make sure the query reflects the country values 'MEX' and 'MEXICO'.</li>
</ul><p>
<img width="960" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/9f2d6a32-c0e2-471f-bced-48dcf343b4a6">
</p>
</p>

----------------------------------------------------------------------------------------------------------------------------
<b>Step 4 (Retrieving employee details in Marketing):</b>
<h4>Sub-Scenario</h4> 
<p>
The security team wants to perform security updates on specific employee machines in the Marketing department. You're responsible for getting information on these employee machines and will need to query the employees table. The department of the employee is found in the <b>department</b> column, which contains values that include Marketing. The office is found in the <b>office</b> column. Some examples of values in this column are East-170, East-320, and North-434.<br>
I'll use the following SQL filters to create a query that identifies all employees in the Marketing department for all offices in the East building:
<ul>
  <li>WHERE</li>
  <li>AND</li>
  <li>LIKE</li>
</ul>
I’ll also use the LIKE keyword with % to filter for the East building.<p>
<img width="483" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/4c030173-314c-48d4-b600-54b3ea026ada">
</p>
</p>

----------------------------------------------------------------------------------------------------------------------------
<b>Step 5 (Retrieving employee details in Finance or Sales):</b>
<h4>Sub-Scenario</h4> 
<p>
The security team now needs to perform a different security update on machines for employees in the Sales and Finance departments. The department of the employees is found in the <b>department</b> column, which contains values that include Sales and Finance.<br>
I'll use the following SQL filters to create a query that identifies all employees in the Sales or Finance departments:
<ul>
  <li>WHERE</li>
  <li>OR</li>
</ul><p>
<img width="960" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/eb21e90c-913b-4def-b303-bfe6d636a5ae">
</p>
</p>

----------------------------------------------------------------------------------------------------------------------------
<b>Step 6 (Retrieving all employee data not in IT):</b>
<h4>Sub-Scenario</h4> 
<p>
The security team needs to make one more update to employee machines. The employees who are in the Information Technology department already had this update, but employees in all other departments need it. The department of the employee is found in the <b>department</b> column, which contains values that include Information Technology.<br>
I'll use the following SQL filters to create a query which identifies all employees not in the IT department:
<ul>
  <li>WHERE</li>
  <li>NOT</li>
</ul><p>
<img width="960" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/fd0a4bb6-fec7-49a0-9a8e-be5624d26695">
</p>
</p>

-----------------------------------------------------------------------------------------------------------------------------
<b>Summary:</b>
<p>
 As a security professional, I have successfully retrieved after-hours failed login attempts, retrieved login attempts on specific dates and those outside Mexico, in addition to retrieving employees data in various departments.<br>This examination of organization’s data using SQL filters has allowed me to retrieve records from different datasets and investigate potential security issues.
</p>
