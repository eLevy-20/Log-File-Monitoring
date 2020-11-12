# Log-File-Monitoring
## Code to analyze and generate reports on the log file. This consists of tracking suspicious activities, irresponsible behavior, system glitches, and domain counts.

### **Creating the Global Dictionary (userlog() function)**
We first wanted to create a global dictionary where the keys would be each user, and the value for each key would be a nested dictionary. The nested dictionary will have the date as the key and the values will be the time, activity, and server. An example would look like {user@domain : {date : [time, activity, server]}}. With this we will be able to go through each line of activity and return specifically what we are looking for. Once we created this, the understandings of the problems became a little more clear to us. The format that we put it into really helped visualizing each component of the original text file. When creating it, we used the ".read" function, but all of the list indexes for the lines of the text file were "out of range." At first we spent a while trying to fix the list, but then realized that we had to change it to ".readlines" so it would already be in a list. 

### **Suspicious Activities** 
This one will be a bit more challenging as there are two parts to the report, if they logged in more than 5 times AND if they logged in between 12 and 5.  Originally we thought it might be best to do both at the same time, but after creating the dicitonary, what it is asking for is a bit more clear. 

Suspicious activities occur when a user logs into the system more than 5 times in one day, or they log on between 12:00 AM and 5:00 AM. We will sort the data firstly through user, then through date, and next through server log within each date. By doing so, we will be able to track the activity of the user. 


### **Irresponsible Behavior**
Irresponsible behavior consists of the user forgetting to log out when they finish using the server. We will track the the number of logins and logouts and compare. If the number of logins is more than the number of logouts then we count the user for irresponsible behavior and track the total amount of this occuring. 

### **System Glitches**
System glitch is very similar to irresonsible behavior except the process is flipped as it is when there are more logouts than logins. In this case, the sytem is glitched and we track it similarly to how we did before. 

### **Domain Counts**
Domain counts tracks how many different names are associated with different email domains. By using the global dictionary,  we will pull out each key value of the outer dictionary and split it by the "@" symbol and assign each side to a varibale. A dictionary will be created with the emails (the second half of the split domain) as the keys and the counts for each name (the first half of the split domain) as the value. The total count (50) will be written into the new file as well. Before the final report, every time we tried to count the number of names to domains, the values in the dictionary would all be 1, which is simply not factual. We solved it by using the "len" function and implementing that at the end of the code. However, it is not in the exact format as the sample; The key values are not in a vertical line. However, we believe it to be as accurate as we can make it, even if it's not perfect and the attempt was made. 

#### Elon Levy, Mason Schwartz
