SObject-Factory
=======================

SObject factory can be used to create test data.

Usage:

    // The SObjectFactory will pre-fill all the fields we typically need
    Account a = (Account)SObjectFactory.createSObject(new Account());
    insert a;
    
    // You can also set values to be used. Any values set in the constructor will override the defaults
    Opportunity o = (Opportunity)SObjectFactory.createSObject(new Opportunity(AccountId = a.Id));
    
    // Finally, get a bunch of records for testing bulk
    Account[] aList = (Account[])SObjectFactory.createSObjectList(new Account(), 200);

    // You can optionally insert records as created like this:
    // Note the final parameter of true.
    Account a = (Account) SObjectFactory.createSObject(new Account(), true);
	Contact c = (Contact) SObjectFactory.createSObject(new Contact(AccountID = a.Id), true);
