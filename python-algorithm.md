<h2>Scenario</h2>
<p>You are a security professional working at a health care company. As part of your job, you're required to regularly update a file that identifies the employees who can access restricted content. The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an allow list for IP addresses permitted to sign into the restricted subnetwork. There's also a remove list that identifies which employees you must remove from this allow list.</p>

<p>Your task is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. If so, you should remove those IP addresses from the file containing the allow list.</p>

<h2>Solution</h2>
<b>Step 1 (Opening the file that contains the allow list):</b>
<p><img width="817" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/44a526f7-f12f-40fc-a63e-5800f3748257">
</p>
<p>The text file 'allow_list.txt' contains a series of IP addresses that are allowed to access restricted information. There are also IP addresses that should no longer have access to this information, and their IP addresses need to be removed from the text file.<br>I assigned these IP adddresses to a variable named 'remove_list' that contains the list of IP addresses to be removed.</p>

<p>As seen in the snapshot above, I displayed both variables to explore their contents.<br>Now I'll move on to opening the 'allow_list.txt' file:</p>
<p>
  <img width="835" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/1b013b7e-2497-49a0-a342-2f3b7a9dc69b">
</p>
<p>This produced an error because the code only contains the first line of the 'with' statement, i.e. opening the file. In following tasks, I'll complete the 'with' statement by reading the file's content and performing a host of other operations on the file.</p>

--------------------------------------------------------------------------------------------------------------------------------------------------------
<b>Step 2 (Reading the file contents):</b>
<p><img width="432" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/a1490438-f7b8-4805-aae7-d9c994bd9484">
</p>
I used the .read() method to read the imported file and then stored it in the 'ip_addresses' variable.<br>

Afterwards, I displayed 'ip_addresses' using the print() function to examine the data in the allow list.

--------------------------------------------------------------------------------------------------------------------------------------------------------
<b>Step 3 (Converting the string into a list):</b>
<p>
  <img width="671" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/7cec1b72-515d-4929-9f78-88e38d58975b">
</p>
I reassigned the ip_addresses variable using the .split() method. This updated the data type from a string to a list, and later on allow me to remove some IP addresses from the allow list.<br>

As usual, I displayed the 'ip_addresses' variable to verify that the update took place.

--------------------------------------------------------------------------------------------------------------------------------------------------------
<b>Step 4 (Iterating through the remove list):</b>
<p>
  <img width="622" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/fb2b6ede-3d68-4ff5-9be5-9c72ea3a20af">
</p>
I need to remove the elements of 'remove_list' from the 'ip_addresses' list, and this will require using an iterative statement.<br>

So I built the iterative statement (for), named the loop variable (element), and looped through 'remove_list'.<br> Finally, I displayed each element in 'remove_list'.

--------------------------------------------------------------------------------------------------------------------------------------------------------
<b>Step 5 (Removing IP addresses that are on the remove list):</b>
<p>
  <img width="546" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/ae2e78d0-9fbb-4486-a8d9-1eb1e0ffb94c">
</p>
I created a conditional statement (if) in the body of the iterative statement to evaluate if the loop variable element is part of the ip_addresses list. This is important to avoid the errors that would occur when using the .remove() method if an element was not part of the ip_addresses list.<br>

Then, within the if statement, I applied the .remove() method to the ip_addresses list and removed the IP addresses identified in the loop variable element.<br>

After the iterative statement removed the elements, I displayed the updated ip_addresses list to verify that the elements of 'remove_list' are no longer in the ip_addresses list.

--------------------------------------------------------------------------------------------------------------------------------------------------------
<b>Step 6 (Updating the file with the revised list of IP addresses):</b>
<p>
  <img width="415" alt="image" src="https://github.com/devhalimah/Google-Cybersecurity-Professional-Certificate-Projects/assets/64546668/eeaa5843-b09c-4782-99ef-a8f5c733101b">
</p>
To update the original file that was used to create the ip_addresses list, I added a line of code containing the .join() method so that the file can be updated. This is necessary because ip_addresses must be in string format when used inside the with statement to rewrite the file.

<p>The .join() method takes in an iterable (such as a list) and concatenates every element of it into a string. The .join() method is applied to a string consisting of the character that will be used to separate every element in the iterable once its converted into a string.<br>As seen in the snapshot above, I applied the .join() method to the string "\n". The "\n" character indicates to separate each element by placing it on a new line. What this means is, it converts 'ip_addresses' from a list back into a string with each IP address on a new line.</p>

<p>After the .join() method, I built the with statement that rewrites the original file using the "w" parameter when calling the open() function. This is to delete the contents in the original file and replace it with the revised list of IP addresses.</p>

<h2>Summary</h2>
<p>
  In this project, I have successfully developed an algorithm that involves opening files and parsing their contents. It checks whether the allow list contains any IP addresses identified on the remove list, and removes those IP addresses from the file containing the allow list.
</p>
