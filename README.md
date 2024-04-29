#  Java 17 Masterclass - unmodifiable collections
Using given code containing **BankAccount** and **BankCustomer** classes (initial commit) create functionality 
for making transactions. To do so you should make the following:
* Create **Transaction** class in dev.dto (data transfer object) package that might mirror a data table
It should have _routingNumber(int), customerId(int), transactionId(long), transactionAmount(double)_
fields with getters and setters. Also, constructor with all fields.
* Modify **BankAccount** so _balance_ is mutable and add _transactions_ collection (ex. Map<Long, transaction>)
with getter. Create method for adding transaction to _transactions_ collection and changing _balance_ 
(_commitTransaction(int routingNumber, long transactionId, String customerId, double amount_)
* Modify **BankCustomer** so it returns _customerId_ as String with 15 digits and leading zeroes. Make class 
not instantiable outside its package. Return defensive copy in _getAccounts_ method. 
Add _getAccount(AccountType type)_ method to get just one account. **Assume that there is only one of each type 
per customer**
* Create **Bank** class with _routingNumber(int), lastTransactionId(long), customers(Map<String, BankCustomer>)_ fields.
Add _getCustomer(String id), addCustomer(String name, double checkingInitialDeposit, double savingsInitialDeposit), 
doTransaction(String id, AccountType type, double amount)_ methods. **Don't let _balance_ go below zero**
* Create **Bank** instance in _main_ method and get **BankCustomer** instance from it. 
Check if this client's transactions are not modifiable from _main_ method