**POCOMaker**
=========

A branch of [EntityFramework Reverse POCO Code First Generator](https://efreversepoco.codeplex.com/) (by Simon Hughes) 
This branch is made to modify naming of navigation properties.

When there are more than one reference to a table, the generator adds a number after the destination table name in the POCO class to name navigation property. For example if we have a Product table which one User orders and another User confirms we'll have:

    class Product
    {
     ...
     public virtual Category Category {get; set;}
     public virtual User User {get; set;}
     public virtual User User1 {get; set;}
    }

To make it meaningful I've made some changes to generate like this:

    class Product
    {
    ...
    public virtual Category Category {get; set;}
    public virtual User User_OrderedBy {get; set;}
    public virtual User User_ConfirmedBy {get; set;}
    }