Assignment #1: Tech Jobs (Console Edition)¶
Implement printJobs
When trying out the program, and later when reading the code, you hopefully noticed that there’s some work to do in the printJobs method. As it stands, it currently just prints a message: "printJobs is not implemented yet".

Complete this method. It should print out something like this:

*****
position type: Data Scientist / Business Intelligence
name: Sr. IT Analyst (Data/BI)
employer: Bull Moose Industries
location: Saint Louis
core competency: Statistical Analysis
*****
If there are no results, it should print an appropriate message.

Tip
To do this, you’ll need to iterate over an ArrayList of jobs. Each job is itself a HashMap. While you can get each of the items out of the HashMap using the known keys (employer, location, etc.), think instead about creating a nested loop to loop over each HashMap. If a new field is added to the job records, this approach will print out the new field without any updates to printJobs.

Test this method before moving on to your next step:

Save your changes.
Select Run from the Run menu and choose to run the TechJobs class (or if you have recently run it, just select the green arrow in the top right corner of the screen).
Select “1” to list the jobs, and then “0” to list them all.
Make sure the printout matches the styling above.
Test that it prints a descriptive message if no jobs are found by selecting “0” to search and then “3” to search for a location. Then enter a location that is not in the data (e.g. “Cancun”). Your message should be displayed.
Create Method findByValue
At this stage, the application will allow users to search a given column of the data for a given String. Your next task is to enable a search that looks for the search term in all of the columns.

In the JobData class, create a new (public static) method that will search for a string within each of the columns. Name it findByValue. Here are a few observations:

The method that you write should not contain duplicate jobs. So, for example, if a listing has position type “Web - Front End” and name “Front end web dev” then searching for “web” should not include the listing twice.
As with printJobs, you should write your code in a way that if a new column is added to the data, your code will automatically search the new column as well.
You should NOT write code that calls findByColumnAndValue once for each column. Rather, utilize loops and collection methods as you did above.
You should, on the other hand, read and understand findByColumnAndValue, since your code will look similar in some ways.
You’ll need to call findByValue from somewhere in main. We’ll leave it up to you to find where. You might have noticed that when you try to search all columns using the app, a message is printed, so that is a good clue to help you find where to place this new method call. Once you find where to call your new method, you can Run the program again to test your code.

Make Search Methods Case-Insensitive
You’ve completed your first two tasks!

Let’s assume you demonstrated the updated application for the Company Team, and they noticed a feature that could be improved. When searching for jobs with the skill JavaScript some results were missing (e.g. the Watchtower Security job on line 31 of the CSV file). The search methods turn out to be case-sensitive, so they treat JavaScript and Javascript as different strings.

The Company Team strongly requested that this needs to be fixed, and of course you told them that you are up to the task.

Here are some questions to ask yourself as you get started:

Which methods are called when searching?
How is the user’s search string compared against the values of fields of the job HashMap objects?
How can you make this comparison in a way that effectively ignores the case of the strings?
How can you do this without altering the capitalization of the items in allJobs so that the data gets printed out the same way that it appears in job_data.csv?
You might find it useful to review the String methods listed in the chapter on Data Types.

When this task is completed, you’re done!

Sanity Check
Before submitting, make sure that your application:

Prints each field of a job when using search functionality, and when listing all columns. If there are no search results, a descriptive message is displayed.
Allows the user to search for a string across all columns.
Returns case-insensitive results.
Solution Demo
Watch a demo of a working solution.


How to Submit
To turn in your assignment and get credit, follow the submission instructions.

Bonus Missions
If you want to take your learning a few steps further, here are some additional problems you can try to solve. We’re not providing you much guidance here, but we have confidence that you can figure these problems out!

Sorting list results: When a user asks for a list of employers, locations, position types, etc., it would be nice if results were sorted alphabetically. Make this happen.
Returning a copy of allJobs: Look at JobData.findAll(). Notice that it’s returning the allJobs property, which is a static property of the JobData class. In general, this is not a great thing to do, since the person calling our findAll method could then mess with the data that allJobs contains. Fix this by creating a copy of allJobs. Hint: Look at the constructors in the Oracle ArrayList documentation.
