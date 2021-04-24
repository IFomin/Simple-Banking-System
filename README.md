# Simple-Banking-System
Everything goes digital these days, and so does money. Today, most people have credit cards, which save us time, energy and nerves. From not having to carry a wallet full of cash to consumer protection, cards make our lives easier in many ways. In this project, you will develop a simple banking system with database.

Let's take a look at the anatomy of a credit card:
The very first digit is the Major Industry Identifier (MII), which tells you what sort of institution issued the card.

1 and 2 are issued by airlines
3 is issued by travel and entertainment
4 and 5 are issued by banking and financial institutions
6 is issued by merchandising and banking
7 is issued by petroleum companies
8 is issued by telecommunications companies
9 is issued by national assignment
In our banking system, credit cards should begin with 4.

The first six digits are the Issuer Identification Number (IIN). These can be used to look up where the card originated from. If you have access to a list that provides detail on who owns each IIN, you can see who issued the card just by reading the card number.

Here are a few you might recognize:
Visa: 4*****
American Express (AMEX): 34**** or 37****
Mastercard: 51**** to 55****
In our banking system, the IIN must be 400000.

The seventh digit to the second-to-last digit is the customer account number. Most companies use just 9 digits for the account numbers, but it’s possible to use up to 12. This means that using the current algorithm for credit cards, the world can issue about a trillion cards before it has to change the system.
We often see 16-digit credit card numbers today, but it’s possible to issue a card with up to 19 digits using the current system. In the future, we may see longer numbers becoming more common.
In our banking system, the customer account number can be any, but it should be unique. And the whole card number should be 16-digit length.
The very last digit of a credit card is the check digit or checksum. It is used to validate the credit card number using the Luhn algorithm, which we will explain in the next stage of this project. For now, the checksum can be any digit you like.

This program customers to create a new account in our banking system.

Once starts, the program print the menu:
1. Create an account
2. Log into account
0. Exit

If the customer chooses ‘Create an account’, program generate a new card number which satisfies all the conditions described above. Then program generate a PIN code that belongs to the generated card number. A PIN code is a sequence of any 4 digits. PIN should be generated in a range from 0000 to 9999.
If the customer chooses ‘Log into account’, program ask them to enter their card information. Program store all generated data until it is terminated so that a user is able to log into any of the created accounts by a card number and its pin.
After all information is entered correctly, program allow the user to check the account balance; right after creating the account, the balance should be 0. It should also be possible to log out of the account and exit the program.

The main purpose of the check digit is to verify that the card number is valid. Say you're buying something online, and you type in your credit card number incorrectly by accidentally swapping two digits, which is one of the most common errors. When the website looks at the number you've entered and applies the Luhn algorithm to the first 15 digits, the result won't match the 16th digit on the number you entered. The computer knows the number is invalid, and it knows the number will be rejected if it tries to submit the purchase for approval, so you're asked to re-enter the number. Another purpose of the check digit is to catch clumsy attempts to create fake credit card numbers. Those who are familiar with the Luhn algorithm, however, could get past this particular security measure.

Luhn Algorithm in action
The Luhn algorithm is used to validate a credit card number or other identifying numbers, such as Social Security. The Luhn algorithm, also called the Luhn formula or modulus 10, checks the sum of the digits in the card number and checks whether the sum matches the expected result or if there is an error in the number sequence. After working through the algorithm, if the total modulus 10 equals zero, then the number is valid according to the Luhn method.

While the algorithm can be used to verify other identification numbers, it is usually associated with credit card verification. The algorithm works for all major credit cards.

It's very upsetting when the data about registered users disappears after the program is completed. To avoid this problem, you need to create a database where you will store all the necessary information about the created credit cards. We will use SQLite to create the database.
SQLite is a database engine. It is a software that allows users to interact with a relational database. In SQLite, a database is stored in a single file — a trait that distinguishes it from other database engines. This allows for greater accessibility: copying a database is no more complicated than copying the file that stores the data, and sharing a database implies just sending an email attachment.

Menu look like this:

1. Balance
2. Add income
3. Do transfer
4. Close account
5. Log out
0. Exit

If the user asks for Balance, you should read the balance of the account from the database and output it into the console.
Add income item should allow us to deposit money to the account.
Do transfer item should allow transferring money to another account. You should handle the following errors:
If the user tries to transfer more money than he/she has, output: Not enough money!
If the user tries to transfer money to the same account, output the following message: You can't transfer money to the same account!
If the receiver's card number doesn’t pass the Luhn algorithm, you should output: Probably you made a mistake in the card number. Please try again!
If the receiver's card number doesn’t exist, you should output: Such a card does not exist.
If there is no error, ask the user how much money they want to transfer and make the transaction.
If the user chooses the Close account item, you should delete that account from the database.
