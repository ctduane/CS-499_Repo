---
title: Christopher Duane's CS-499 Capstone Site
---

## Professional Self-Assessment
blah blah insert self assessment here

## Code Review

<div align="center">
	<iframe width="400" height="300" src="https://youtube.com/embed/Gdv9MdSamLo" allowFullscreen></iframe>
</div>

## Enhancement One - Software Design and Engineering
<p style="text-indent:3em">
The artifact that I chose to enhance is a project from IT-145: Foundation in Application Development. I decided that I would use this project to demonstrate all three enhancement categories. The chosen artifact is a rescue animal management system for a fake rescue animal company known as “Grazioso Salvare”. It allows the user to add rescue animals (dogs and monkeys) to the system, view all the animals, and reserve an animal through a text-based interface. It was created some time around 2021, I believe, as one of the first projects I created in a computer science program.
</p>
<p style="text-indent:3em">	
I decided to choose this item because I felt like it had a good foundation, at least conceptually, to expand upon. While the program is super simple, it includes concepts like a basic user interface, menu control, and data storage/management. I believe it was something we were tasked with creating because it provided a good foundation for understanding object-oriented programming principles, including inheritance (Dog and Monkey inheriting from RescueAnimal) with some unique attributes, class separation, and simple data structures (ArrayLists for the animal storage). 
</p>
<p style="text-indent:3em">
The improvements I made in the software design and engineering category essentially revolved around a complete redesign of the project in the form of an Android application. While the language, Java, remained the same, the Android application functions in an entirely different manner while maintaining the same core idea – viewing, updating, and adding rescue animals to the management system. 
</p>
<p style="text-indent:3em">
I restructured the rescue animal management system into a basic android Application that displays all of the animals’ information using a dynamically updating table. A floating action button (FAB) is displayed in the bottom-right corner of the interface, which opens up a dialog when pressed. This dialog is a form to add a new rescue animal to the database, acquiring all the animal’s attributes through a series of edit texts, radio buttons, a date picker, and country picker. The dialog ensures that all the required attributes have been entered before attempting to add the animal to the database, and provides warnings to the user indicating when they have left a field empty. Once the information has been entered and is valid, the user can confirm the entry through a button at the bottom, which will update the database and the table, displaying the new animal immediately.
</p>
<p style="text-indent:3em">
I ran into quite a few problems while working on this enhancement. I initially attempted to implement the table through the use of multiple recycler views, following some examples online and through the Android Studio Gemini assistant plugin. This turned out to be much more complex than necessary and only caused me problems (I couldn’t get even a single entry in the database to display properly), so I restructured the project around a plugin I found called TableView on GitHub. This proved to be a much more modular and straightforward foundation for the application, although I ran into some issues that were not addressed in their documentation. Thankfully, the GitHub repo itself had an issues post where someone had the exact some problem that I was having which is not mentioned in the documentation’s setup instructions. I was able to fix my issue by simply setting a parameter in the TableView’s .xml file. 
</p>
<p style="text-indent:3em">
Aside from that, most of my issues revolved around unfamiliarity with Android development, re-familiarizing myself with Android Studio, and attempting to implement features that I had never used before. This included things like the table only updating after the application had been reloaded, because I was not calling the method with the correct parameters to update it immediately, forgetting simple things like dismissing the dialog after pressing the confirm button, app crashes caused by the fact I had created view elements that I forgot to set to their respective .xml counterparts, and proceeded to call methods on null objects, and more fun stuff. My main goal with this iteration of the project was to get the core functionality of the original program implemented, and in future iterations I wanted to implement an efficient search algorithm that updates the table, a username/password database, as well as the ability to edit individual rows in the table.
</p>
<p style="text-indent:3em">
I believe I have met the outcomes I planned in module one, as this enhancement was mostly focused on my ability to develop an application following industry-standard best practices and techniques. I learned quite a bit while working on this section of the enhancement, as I’m still quite new to Android development. I’ve only ever taken one class in the subject, but I felt like this would be a good learning opportunity and an interesting conversion of the artifact. 
</p>

## Enhancement Two - Data Structures and Algorithms
<p style="text-indent:3em;">
For the data structures and algorithms enhancement of the rescue animal management system, I implemented sorting for the columns in the table, a search function, as well as expanded upon the user database by creating login and register pages that use hashing algorithms to store passwords safely.
</p>
<p style="text-indent:3em;">
Tapping on a column name at the top of the table sorts the table based off ascending/descending order. The search bar at the top searches for anything in the table matching the keyword, meaning you don’t have to specify the type of value you’re looking for. Honestly, this is something that could be expanded upon further by including specific column searches instead of the entire table, but that was beyond the scope of my planned improvements. I utilized the BCrypt library from the Spring framework for the password hashing – it hashes the user’s password with a salt and stores that instead of the plaintext password. That way, if someone gets access to the passwords in the user database, they still wouldn’t be able to login.
</p>
<p style="text-indent:3em;">
This enhancement was a bit difficult at times, but the TableView library I am utilizing has a wide range of functionality that perfectly fit my desired enhancements. I mainly followed the TableView and BCrypt documentation and used my past Android app project as a reference to implement the enhancements. I had a few problems related to the searching functionality, as any searched value would result in the table being blank. The problem ended up being that my data model for the cells in the table was incorrectly returning the filterable keyword, and I needed to return the data in the cell as a string.
</p>
<p style="text-indent:3em;">
I had a similar issue with the column sorting functionality, as some of the rows in the table would get overwritten and I’d end up having duplicates. The problem ended up being that my cell model was incorrectly assigning unique IDs to the cells in the table, so some of them got overwritten during sorting. I ended up setting an ID for each cell in the constructor using the randomUUID method from java.util.UUID, which fixed my problem.
</p>
<p style="text-indent:3em;">
I mentioned this in the previous enhancement, but I am still relatively new to Android development. At this point I was still trying to get familiar with the environment, and it was certainly frustrating at times. However, I do feel like I have slowly become more accustomed to the Android development process and I simply need to put more time into fleshing these things out.
I believe I met the outcomes I planned for this enhancement back in module one – I had planned a search functionality for the database and to move all the animals into a single data structure, which has been accomplished as of this point.
</p>

## Enhancement Three - Databases
<p style="text-indent:3em;">
The final enhancement was in the databases category – this enhancement was touched upon a bit in the previous submissions, as I needed the database to function in order to implement some of the system design and data structures/algorithms functionality. However, I did continue to improve upon it in the database category.
</p>
<p style="text-indent:3em;">
I had already implemented the “C” in CRUD (Create) for the database in a previous module, so this time I included a few new features for the Android application, related to the “RUD” (Read, Update, Delete). In order to delete items, I added a checkbox at the beginning of each row that allows the user to select multiple entries in the table. This works in conjunction with the new menu bar at the top, which has an option to delete all of the checked rows. The user can check as many rows as they want, then tap the menu option to delete them, and they will subsequently be removed both from the interface and the database.
</p>
<p style="text-indent:3em;">
For reading and updating, I added a feature to long press on any cell in a row. When a cell is long pressed, a dialog will pop up with all of the information contained in that row, which can be used to either read the information or to update the information for the row. 
</p>
<p style="text-indent:3em;">
I ran into many issues during my work on this enhancement, including (but not limited to): Deleting items from the list of rows while iterating through them leading to an index out of bounds error, general confusion regarding how to transfer information between the TableViewListener, the MainActivity, the EditAnimalDialogFragment, and then back to the MainActivity, forgetting to refresh the table when deleting an item so it appears to still be there, forgetting to initialize an interface so attempting to view an item’s details led to a null pointer exception, and more.
</p>

