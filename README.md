# Log-File-Monitoring
## Code to analyze and generate reports on the log file. This consists of tracking suspicious activities, irresponsible behavior, system glitches, and domain counts.

### **Suspicious Activities** 
Suspicious activities occur when a user logs into the system more than 5 times in one day, or they log on between 12:00 AM and 5:00 AM. We will sort the data firstly through user, then through date, and next through server log within each date. By doing so, we will be able to track the activity of the user.

### **Irresponsible Behavior**
Irresponsible behavior consists of the user forgetting to log out when they finish using the server. We will track the the number of logins and logouts and compare. If the number of logins is more than the number of logouts then we count the user for irresponsible behavior and track the total amount of this occuring. 

### **System Glitches**
System glitch is very similar to irresonsible behavior except the process is flipped as it is when there are more logouts than logins. In this case, the sytem is glitched and we track it similarly to how we did before. 

### **Domain Counts**
Domain counts tracks how many different names are associated with different email domains. Split each user at the "@" symbol and then count names per domain in a dictionary.

#### Elon Levy, Mason Schwartz
