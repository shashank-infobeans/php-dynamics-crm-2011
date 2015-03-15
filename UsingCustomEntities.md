# Introduction #

When using custom entities that have been created by your business, there is usually not a specific Class in the DynamicsCRM2011 library to represent this entity.
This is also true of a large portion of the standard entities that exist by default.

However, even though no dedicated class exists to handle these entities, it is still possible to use them in `create()`, `update()`, `retrieve()` and `retrieveMultiple()` requests, just like the entities with dedicated classes.

# Details #

All entities defined in DynamicsCRM2011 are subclasses of the generic `DynamicsCRM2011_Entity` class.  In fact, this class can handle automatically any Entity that exists on the Microsoft Dynamics CRM 2011 system.

For example, although a class exists for Contacts (`DynamicsCRM2011_Contact`), a Contact object could be created instead using the generic Entity class as follows:
```php

$new_contact = new DynamicsCRM2011_Entity($crmConnector, 'contact');
```

When using `retrieve()` and `retrieveMultiple()`, the system will automatically create Entities in this way where a specific class does not exist for your returned data.

These Entities can be used in exactly the same way as a strongly typed Entity in `create()`, `update()`, `retrieve()` and `retrieveRecordChangeHistory()` requests; there is no difference internally.

The few advantages of a strongly typed entity are:
  * Conversion of an entity to a string (using `__toString()`) can be more type-appropriate
  * Restriction on passing certain Entities to other functions (i.e. `function email_contact(DynamicsCRM2011_Contact $contact)` would only accept a Contact, not a Lead
  * Better code clarity and understandability
  * Some strongly-typed Entities (e.g. `DynamicsCRM2011_KBArticle` for a knowledgebase article) have entity-specific functions