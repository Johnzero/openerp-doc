
=====================
Business Applications
=====================

Defining new applications or completing existing ones
+++++++++++++++++++++++++++++++++++++++++++++++++++++

We usually try to define new business applications related to job positions in the enterprise. These are good examples of applications: Purchase, Sales, Accounting and Project. Don't create business application by features. These are bad examples of business applications: lunch orders management, expenses sheets, etc.

If you have specific features that don't belong in the existing business applications, you can put them in the “Miscelleanous Tools” application.

Configuration wizards of business applications.
+++++++++++++++++++++++++++++++++++++++++++++++

Each application must create an entry in the main base_setup wizard that shows all the possible business applications defined in quality certified modules only.

.. figure:: Pictures/1.2.Installation_of_modules.png
   :align: center


You can also create one configuration wizard dedicated to your business application. For example, when you install project management, you get this wizard:

.. figure:: Pictures/1.3.Project_management.png
   :align: center


Business Applications must be complete
++++++++++++++++++++++++++++++++++++++

Each user/role must be able to perform most of their tasks from one business application. For example, a salesman should see in his menu: Leads, Opportunities, Meetings, Sales Orders, Sales to Invoice, etc. He should not be forced to go to the accounting application to invoice the sales.

Transversal features, used by all applications
++++++++++++++++++++++++++++++++++++++++++++++

Some features should be accessible by all users, regardless of which application they usually work in. For example, most users should have access to: Partners, Agenda of Meetings, Products. In that case, you put the menu in the applications that needs these features more. (Example: the address book is in the sales, purchases and accounting application)
And, these features must be set as shortcuts for every user in the system by default, at the creation of the user.

Access Rights must define groups per application.
+++++++++++++++++++++++++++++++++++++++++++++++++

The groups defined by each module must be directly related to business application. So, if you have an application which is “Accounting”.  All groups within this application must be like: “Accounting / Accountant”, “Accounting / Financial Manager”, etc.


One dashboard defined per application
+++++++++++++++++++++++++++++++++++++

Each business application must have one dashboard attached to its root menu item. When a user enters a business application, they should see the dashboard related to this application.




