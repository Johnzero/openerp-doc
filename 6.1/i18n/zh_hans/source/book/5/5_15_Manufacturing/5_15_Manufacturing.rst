
.. i18n: Manufacturing Orders
.. i18n: ====================
..

Manufacturing Orders
====================

.. i18n: Once the bills of materials have been defined, OpenERP is capable of automatically deciding on the manufacturing route according to the needs of the company.
..

Once the bills of materials have been defined, OpenERP is capable of automatically deciding on the manufacturing route according to the needs of the company.

.. i18n: Production orders can be proposed automatically by the system depending on several criteria described in the preceding chapter:
..

Production orders can be proposed automatically by the system depending on several criteria described in the preceding chapter:

.. i18n: * Using the ``Make to Order`` rules,
.. i18n: 
.. i18n: * Using the ``Order Point`` (Minimum Stock) rules,
.. i18n: 
.. i18n: * Using the Production plan.
..

* Using the ``Make to Order`` rules,

* Using the ``Order Point`` (Minimum Stock) rules,

* Using the Production plan.

.. i18n: Of course, you can also start production manually by clicking the button :guilabel:`New` in the menu :menuselection:`Manufacturing --> Manufacturing --> Manufacturing Orders`.
..

Of course, you can also start production manually by clicking the button :guilabel:`New` in the menu :menuselection:`Manufacturing --> Manufacturing --> Manufacturing Orders`.

.. i18n: .. figure:: images/mrp_manual.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *Manufacturing Order*
..

.. figure:: images/mrp_manual.png
   :scale: 75
   :align: center

   *Manufacturing Order*

.. i18n: .. index::
.. i18n:    single: module; mrp_jit
..

.. index::
   single: module; mrp_jit

.. i18n: If you have not installed the Just-in-Time planning module :mod:`mrp_jit`, you should start using OpenERP to schedule the Production Orders automatically using the various system rules. To do this, use the menu :menuselection:`Warehouse --> Schedulers --> Compute Schedulers`.
..

If you have not installed the Just-in-Time planning module :mod:`mrp_jit`, you should start using OpenERP to schedule the Production Orders automatically using the various system rules. To do this, use the menu :menuselection:`Warehouse --> Schedulers --> Compute Schedulers`.

.. i18n: .. tip:: Procurement Exceptions
.. i18n: 
.. i18n:         Pay attention to the fact that you have to define `minimum stock rules` for each product set as ``Make to Stock``.
..

.. tip:: Procurement Exceptions

        Pay attention to the fact that you have to define `minimum stock rules` for each product set as ``Make to Stock``.

.. i18n: Complete Production Workflow
.. i18n: ============================
..

Complete Production Workflow
============================

.. i18n: To understand the usefulness and the functioning of the system you should test a complete workflow
.. i18n: on the database installed with the demonstration data. We will show you:
..

To understand the usefulness and the functioning of the system you should test a complete workflow
on the database installed with the demonstration data. We will show you:

.. i18n: * How to create a sales order,
.. i18n: 
.. i18n: * The manufacturing workflow for an intermediate product,
.. i18n: 
.. i18n: * The manufacturing of an ordered product,
.. i18n: 
.. i18n: * The delivery of products to a customer,
.. i18n: 
.. i18n: * Invoicing at the end of the month,
.. i18n: 
.. i18n: * Traceability for after-sales service.
..

* How to create a sales order,

* The manufacturing workflow for an intermediate product,

* The manufacturing of an ordered product,

* The delivery of products to a customer,

* Invoicing at the end of the month,

* Traceability for after-sales service.

.. i18n: .. tip:: Demonstration data
.. i18n: 
.. i18n:     To exactly follow the workflow as shown below, you should keep the same quantities as in the
.. i18n:     example and start from a new database. Then you will not run into exceptions resulting from a lack of stock.
..

.. tip:: Demonstration data

    To exactly follow the workflow as shown below, you should keep the same quantities as in the
    example and start from a new database. Then you will not run into exceptions resulting from a lack of stock.

.. i18n: This more advanced case of handling problems in procurement will be sorted out later in the chapter.
..

This more advanced case of handling problems in procurement will be sorted out later in the chapter.

.. i18n: To be able to do the following step, add ``Sales Management`` through the Reconfigure wizard.
..

To be able to do the following step, add ``Sales Management`` through the Reconfigure wizard.

.. i18n: The Sales Order
.. i18n: +++++++++++++++
..

The Sales Order
+++++++++++++++

.. i18n: .. index:: quotation
.. i18n: .. index:: sales order
..

.. index:: quotation
.. index:: sales order

.. i18n: Begin by encoding a sales (or customer) order through the menu :menuselection:`Sales --> Sales Orders -> New Quotation`. Enter the following information:
..

Begin by encoding a sales (or customer) order through the menu :menuselection:`Sales --> Sales Orders -> New Quotation`. Enter the following information:

.. i18n: * :guilabel:`Customer` : Agrolait,
.. i18n: 
.. i18n: * :guilabel:`Shipping Policy` : Invoice from the picking (``Other Information`` tab),
.. i18n: 
.. i18n: * :guilabel:`Sales Order Lines`, click `New`:
.. i18n: 
.. i18n:   * :guilabel:`Product` : PC2 – Basic PC (assembly on order),
.. i18n: 
.. i18n:   * :guilabel:`Quantity (UoM)` : 1,
.. i18n: 
.. i18n:   * :guilabel:`Product UoM` : PCE,
.. i18n: 
.. i18n:   * :guilabel:`Procurement Method` : on order.
..

* :guilabel:`Customer` : Agrolait,

* :guilabel:`Shipping Policy` : Invoice from the picking (``Other Information`` tab),

* :guilabel:`Sales Order Lines`, click `New`:

  * :guilabel:`Product` : PC2 – Basic PC (assembly on order),

  * :guilabel:`Quantity (UoM)` : 1,

  * :guilabel:`Product UoM` : PCE,

  * :guilabel:`Procurement Method` : on order.

.. i18n: Once the quotation has been entered, you can confirm it immediately by clicking the button
.. i18n: :guilabel:`Confirm Order` at the bottom to the right. Keep note of the order reference because this
.. i18n: follows all through the process. Usually, in a new database, this will be ``SO007`` . At this stage,
.. i18n: you can look at the process linked to your order using the :guilabel:`Question Mark` button next to the ``Sales Orders`` title.
..

Once the quotation has been entered, you can confirm it immediately by clicking the button
:guilabel:`Confirm Order` at the bottom to the right. Keep note of the order reference because this
follows all through the process. Usually, in a new database, this will be ``SO007`` . At this stage,
you can look at the process linked to your order using the :guilabel:`Question Mark` button next to the ``Sales Orders`` title.

.. i18n: .. figure:: images/mrp_sales_process_new.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *Process for Handling Sales Order SO007*
..

.. figure:: images/mrp_sales_process_new.png
   :scale: 75
   :align: center

   *Process for Handling Sales Order SO007*

.. i18n: Start the requirements calculation using the menu :menuselection:`Manufacturing --> Compute All Schedulers`.
..

Start the requirements calculation using the menu :menuselection:`Manufacturing --> Compute All Schedulers`.

.. i18n: .. index::
.. i18n:    single: semi-finished product
..

.. index::
   single: semi-finished product

.. i18n: Producing an Intermediate Product
.. i18n: +++++++++++++++++++++++++++++++++
..

Producing an Intermediate Product
+++++++++++++++++++++++++++++++++

.. i18n: To understand the implications of requirements calculation, you should know the configuration of the sold product. To do this, go to the form for product PC2 and click the link :guilabel:`Product BoM Structure` to the right. You get the scheme shown in :ref:`fig-mrpbomtree` which is the composition of the selected product.
..

To understand the implications of requirements calculation, you should know the configuration of the sold product. To do this, go to the form for product PC2 and click the link :guilabel:`Product BoM Structure` to the right. You get the scheme shown in :ref:`fig-mrpbomtree` which is the composition of the selected product.

.. i18n: .. _fig-mrpbomtree:
.. i18n: 
.. i18n: .. figure:: images/mrp_product_bom_tree_new.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *Composition of PC2*
..

.. _fig-mrpbomtree:

.. figure:: images/mrp_product_bom_tree_new.png
   :scale: 75
   :align: center

   *Composition of PC2*

.. i18n: The PC2 computer has to be manufactured in two steps:
..

The PC2 computer has to be manufactured in two steps:

.. i18n: 1: The intermediate product: CPU_GEN
..

1: The intermediate product: CPU_GEN

.. i18n: 2: The finished product using that intermediate product: PC2
..

2: The finished product using that intermediate product: PC2

.. i18n: The manufacturing supervisor can then consult the production orders using the menu
.. i18n: :menuselection:`Manufacturing --> Manufacturing --> Manufacturing Orders`. You then get a
.. i18n: list of orders to start (``Ready to Produce``) and the estimated start date (``Scheduled Date``) to meet the customer delivery date.
..

The manufacturing supervisor can then consult the production orders using the menu
:menuselection:`Manufacturing --> Manufacturing --> Manufacturing Orders`. You then get a
list of orders to start (``Ready to Produce``) and the estimated start date (``Scheduled Date``) to meet the customer delivery date.

.. i18n: .. figure:: images/mrp_production_list_new.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *List of Manufacturing Orders*
..

.. figure:: images/mrp_production_list_new.png
   :scale: 75
   :align: center

   *List of Manufacturing Orders*

.. i18n: You will see the production order for CPU_GEN, but not the one for PC2 because it depends on an intermediate product that has to be produced first. Return to the production order for CPU_GEN and click it. If there are several of them, select the one corresponding to your order using the source document that contains your order number (in this example ``SO007`` ).
..

You will see the production order for CPU_GEN, but not the one for PC2 because it depends on an intermediate product that has to be produced first. Return to the production order for CPU_GEN and click it. If there are several of them, select the one corresponding to your order using the source document that contains your order number (in this example ``SO007`` ).

.. i18n: .. figure:: images/mrp_production_form_new.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *Details of a Production Order*
..

.. figure:: images/mrp_production_form_new.png
   :scale: 75
   :align: center

   *Details of a Production Order*

.. i18n: The system shows you that you have to manufacture product CPU_GEN using the components: MB1, CPU1, FAN, RAM. You can then confirm the production twice:
..

The system shows you that you have to manufacture product CPU_GEN using the components: MB1, CPU1, FAN, RAM. You can then confirm the production twice:

.. i18n: Start production: consumption of raw materials,
..

Start production: consumption of raw materials,

.. i18n: Produce: manufacturing of finished product.
..

Produce: manufacturing of finished product.

.. i18n: Click the ``Start Production`` button, then click the ``Edit`` button, and edit the line for the product MB1. Enter a lot number for it by putting the cursor in the field :guilabel:`Production Lot` and pressing :kbd:`<F1>` to create a new lot. Enter an internal reference, for example: ``MB1345678``. The system may then show you a warning because this lot is not in stock, but you can ignore this message.
..

Click the ``Start Production`` button, then click the ``Edit`` button, and edit the line for the product MB1. Enter a lot number for it by putting the cursor in the field :guilabel:`Production Lot` and pressing :kbd:`<F1>` to create a new lot. Enter an internal reference, for example: ``MB1345678``. The system may then show you a warning because this lot is not in stock, but you can ignore this message.

.. i18n: Click the ``Produce`` button to manufacture the finished product.
..

Click the ``Produce`` button to manufacture the finished product.

.. i18n: The production order has to be in the closed state as shown in the figure :ref:`fig-mrpprdfrm`.
..

The production order has to be in the closed state as shown in the figure :ref:`fig-mrpprdfrm`.

.. i18n: .. _fig-mrpprdfrm:
.. i18n: 
.. i18n: .. figure:: images/mrp_production_form_end_new.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *Production Order after the Different Stages*
..

.. _fig-mrpprdfrm:

.. figure:: images/mrp_production_form_end_new.png
   :scale: 75
   :align: center

   *Production Order after the Different Stages*

.. i18n: Finished Product Manufacturing
.. i18n: ++++++++++++++++++++++++++++++
..

Finished Product Manufacturing
++++++++++++++++++++++++++++++

.. i18n: Having manufactured the intermediate product CPU_GEN, OpenERP automatically proposes the manufacturing
.. i18n: of the computer PC2 using the order created earlier. Return to the Manufacturing Orders menu and look at the orders Ready to Produce through  :menuselection:`Manufacturing --> Manufacturing --> Manufacturing Orders`.
..

Having manufactured the intermediate product CPU_GEN, OpenERP automatically proposes the manufacturing
of the computer PC2 using the order created earlier. Return to the Manufacturing Orders menu and look at the orders Ready to Produce through  :menuselection:`Manufacturing --> Manufacturing --> Manufacturing Orders`.

.. i18n: You will find computer PC2 which has been sold to the customer (source document SO007), as shown in the figure hereafter.
..

You will find computer PC2 which has been sold to the customer (source document SO007), as shown in the figure hereafter.

.. i18n: .. figure:: images/mrp_production_list_end_new.png
.. i18n:     :scale: 75
.. i18n:     :align: center
.. i18n:     
.. i18n:     *Completed Production for PC2*
..

.. figure:: images/mrp_production_list_end_new.png
    :scale: 75
    :align: center
    
    *Completed Production for PC2*

.. i18n: Now that the production has been completed, the product sold to the customer has been manufactured and the raw materials have been consumed and taken out of stock.
.. i18n:  
.. i18n: .. tip:: Automatic Actions
.. i18n: 
.. i18n:     As well as managing the use of materials and the production of stocks, manufacturing can have the following
.. i18n:     automatic effects which are detailed further on in the chapter:
.. i18n:     
.. i18n:     * adding value to stock,
.. i18n:     * generating operations for assembly staff,
.. i18n:     * automatically creating analytical accounting entries.
..

Now that the production has been completed, the product sold to the customer has been manufactured and the raw materials have been consumed and taken out of stock.
 
.. tip:: Automatic Actions

    As well as managing the use of materials and the production of stocks, manufacturing can have the following
    automatic effects which are detailed further on in the chapter:
    
    * adding value to stock,
    * generating operations for assembly staff,
    * automatically creating analytical accounting entries.

.. i18n: Subproduct Production
.. i18n: +++++++++++++++++++++
..

Subproduct Production
+++++++++++++++++++++

.. i18n: If you need to manage subproducts, you should install the module :mod:`mrp_subproduct` (Reconfigure wizard, MRP Sub-
.. i18n: products). The normal behaviour of manufacturing in OpenERP enables you to manufacture several units of the
.. i18n: same finished product from raw materials (A + B > C). With Subproduct management, the manufacturing result can be to have both finished products and secondary products (A + B > C + D).
..

If you need to manage subproducts, you should install the module :mod:`mrp_subproduct` (Reconfigure wizard, MRP Sub-
products). The normal behaviour of manufacturing in OpenERP enables you to manufacture several units of the
same finished product from raw materials (A + B > C). With Subproduct management, the manufacturing result can be to have both finished products and secondary products (A + B > C + D).

.. i18n: .. note:: Subproduct Material
.. i18n: 
.. i18n:     In OpenERP, subproduct material corresponds to secondary products that are a by-product of the main manufacturing
.. i18n:     process. For example, cutting planks of timber will produce other planks but these bits of timber are too small 
.. i18n:     (or the offcuts may have value for the company if they can be used elsewhere).
..

.. note:: Subproduct Material

    In OpenERP, subproduct material corresponds to secondary products that are a by-product of the main manufacturing
    process. For example, cutting planks of timber will produce other planks but these bits of timber are too small 
    (or the offcuts may have value for the company if they can be used elsewhere).

.. i18n: If the module :mod:`mrp_subproduct` has been installed, you get a new tab Sub products in the Bill of Material
.. i18n: that lets you set secondary products resulting from the manufacturing of the finished product.
..

If the module :mod:`mrp_subproduct` has been installed, you get a new tab Sub products in the Bill of Material
that lets you set secondary products resulting from the manufacturing of the finished product.

.. i18n: .. figure:: images/mrp_bom_subproduct.png
.. i18n:     :scale: 75
.. i18n:     :align: center
.. i18n:     
.. i18n:     *Definition of Subproducts*
..

.. figure:: images/mrp_bom_subproduct.png
    :scale: 75
    :align: center
    
    *Definition of Subproducts*

.. i18n: When OpenERP generates a production order based on a bill of materials that uses a secondary product, you pick
.. i18n: up the list of all products in the second tab of the production order ``Finished Products``.
.. i18n:     
.. i18n: .. figure:: images/mrp_production.png
.. i18n:     :scale: 75
.. i18n:     :align: center
.. i18n:     
.. i18n:     *Production Order producing Several Finished Products*
..

When OpenERP generates a production order based on a bill of materials that uses a secondary product, you pick
up the list of all products in the second tab of the production order ``Finished Products``.
    
.. figure:: images/mrp_production.png
    :scale: 75
    :align: center
    
    *Production Order producing Several Finished Products*

.. i18n: Secondary products enable you to generate several types of products from the same raw materials and manufacturing methods - only these are not used in the calculation of requirements. Then, if you need the secondary products, OpenERP will not ask you to manufacture another product to use the waste products and secondary products of this production. In this case, you should enter another production order for the secondary product.
..

Secondary products enable you to generate several types of products from the same raw materials and manufacturing methods - only these are not used in the calculation of requirements. Then, if you need the secondary products, OpenERP will not ask you to manufacture another product to use the waste products and secondary products of this production. In this case, you should enter another production order for the secondary product.

.. i18n: .. note:: Services in Manufacturing
.. i18n: 
.. i18n:     Unlike most software for production management, OpenERP manages services as well as stockable products. So
.. i18n:     it is possible to put products of type Service in a bill of materials. These do not appear in the production 
.. i18n:     order, but their requirements will be taken into account.
.. i18n:     
.. i18n:     If they are defined as Make to Order, OpenERP will generate a task for the manufacturing or a subcontract
.. i18n:     order for the operations. The behaviour will depend on the Supply Method configured in the product form: Buy
.. i18n:     or Produce.
..

.. note:: Services in Manufacturing

    Unlike most software for production management, OpenERP manages services as well as stockable products. So
    it is possible to put products of type Service in a bill of materials. These do not appear in the production 
    order, but their requirements will be taken into account.
    
    If they are defined as Make to Order, OpenERP will generate a task for the manufacturing or a subcontract
    order for the operations. The behaviour will depend on the Supply Method configured in the product form: Buy
    or Produce.

.. i18n: Scrapping
.. i18n: +++++++++
..

Scrapping
+++++++++

.. i18n: If you have to scrap the final product before it is finished, you will have to scrap every component allowed for this product. 
..

If you have to scrap the final product before it is finished, you will have to scrap every component allowed for this product. 

.. i18n: .. figure:: images/mo_scrap.png
.. i18n:     :scale: 75
.. i18n:     :align: center
.. i18n:     
.. i18n:     *Scrapping a Product to Finish*
..

.. figure:: images/mo_scrap.png
    :scale: 75
    :align: center
    
    *Scrapping a Product to Finish*

.. i18n: If you scrap a Product to Finish, you will get the situation illustrated in the previous figure. A finished product will be *created* and put in the scrapped virtual location. A new Product to Finish has been added to the manufacturing order.
..

If you scrap a Product to Finish, you will get the situation illustrated in the previous figure. A finished product will be *created* and put in the scrapped virtual location. A new Product to Finish has been added to the manufacturing order.

.. i18n: .. tip:: Scrap a product
.. i18n: 
.. i18n:     To scrap a product, you have to edit the manufacturing order and then select the product to be
.. i18n:     scrapped by clicking the little pencil at the left of the item.
..

.. tip:: Scrap a product

    To scrap a product, you have to edit the manufacturing order and then select the product to be
    scrapped by clicking the little pencil at the left of the item.

.. i18n: This new product has been added for the following reason: when you have to manufacture a product and if this product
.. i18n: has to be scrapped, you have to produce another product to replace the scrapped one. The reason why 
.. i18n: you have to scrap each component manually is that the production problem can come from one component.
..

This new product has been added for the following reason: when you have to manufacture a product and if this product
has to be scrapped, you have to produce another product to replace the scrapped one. The reason why 
you have to scrap each component manually is that the production problem can come from one component.

.. i18n: If the production process is finished and you see that you have to scrap the finished product, you will
.. i18n: not have to scrap the different components. They are already *consumed*. They are not available anymore
.. i18n: for further manufacturing orders; they have been moved to the production Stock Location.
..

If the production process is finished and you see that you have to scrap the finished product, you will
not have to scrap the different components. They are already *consumed*. They are not available anymore
for further manufacturing orders; they have been moved to the production Stock Location.

.. i18n: Production Orders
.. i18n: +++++++++++++++++
..

Production Orders
+++++++++++++++++

.. i18n: To open a Production Order, use the menu :menuselection:`Manufacturing --> Manufacturing --> Manufacturing Orders` and click the `New` button.
.. i18n: You get a blank form to enter a new production order as shown in the figure :ref:`fig-mrpprdnew`.
..

To open a Production Order, use the menu :menuselection:`Manufacturing --> Manufacturing --> Manufacturing Orders` and click the `New` button.
You get a blank form to enter a new production order as shown in the figure :ref:`fig-mrpprdnew`.

.. i18n: .. _fig-mrpprdnew:
.. i18n: 
.. i18n: .. figure:: images/mrp_production_new.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *New Production Order*
..

.. _fig-mrpprdnew:

.. figure:: images/mrp_production_new.png
   :scale: 75
   :align: center

   *New Production Order*

.. i18n: The production order follows the process given by the figure :ref:`fig-mrpprdproc`.
..

The production order follows the process given by the figure :ref:`fig-mrpprdproc`.

.. i18n: .. _fig-mrpprdproc:
.. i18n: 
.. i18n: .. figure:: images/mrp_production_processus.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *Process for Handling a Production Order*
..

.. _fig-mrpprdproc:

.. figure:: images/mrp_production_processus.png
   :scale: 75
   :align: center

   *Process for Handling a Production Order*

.. i18n: The `Scheduled date` , `Product Qty` and `Reference`, are automatically completed when the form is first opened.
.. i18n: Enter the product that you want to produce, and the quantity required. The :guilabel:`Product UOM` by
.. i18n: default is completed automatically by OpenERP when the product is first selected.
..

The `Scheduled date` , `Product Qty` and `Reference`, are automatically completed when the form is first opened.
Enter the product that you want to produce, and the quantity required. The :guilabel:`Product UOM` by
default is completed automatically by OpenERP when the product is first selected.

.. i18n: You then have to set two locations:
..

You then have to set two locations:

.. i18n: 	* The location from which the required raw materials should be found, and
.. i18n: 
.. i18n: 	* The location for depositing the finished products.
..

	* The location from which the required raw materials should be found, and

	* The location for depositing the finished products.

.. i18n: For simplicity, put the ``Stock`` location in both places. The field :guilabel:`Bill of Materials` will
.. i18n: automatically be completed by OpenERP when you select the product. You can then overwrite it with another BoM to specify something else to use for this specific manufacturing, then click the button :guilabel:`Compute Data`.
..

For simplicity, put the ``Stock`` location in both places. The field :guilabel:`Bill of Materials` will
automatically be completed by OpenERP when you select the product. You can then overwrite it with another BoM to specify something else to use for this specific manufacturing, then click the button :guilabel:`Compute Data`.

.. i18n: The tabs :guilabel:`Scheduled Products` and :guilabel:`Work Orders` are also completed automatically when you click
.. i18n: :guilabel:`Compute Data` (in the :guilabel:`Work Orders` or :guilabel:`Scheduled Products` tabs). 
.. i18n: You will find the raw materials there that are required for the production and the operations needed by the assembly staff.
..

The tabs :guilabel:`Scheduled Products` and :guilabel:`Work Orders` are also completed automatically when you click
:guilabel:`Compute Data` (in the :guilabel:`Work Orders` or :guilabel:`Scheduled Products` tabs). 
You will find the raw materials there that are required for the production and the operations needed by the assembly staff.

.. i18n: If you want to start production, click the button :guilabel:`Confirm Production`, and OpenERP automatically completes the :guilabel:`Products to Consume` field in the :guilabel:`Consumed Products` tab and :guilabel:`Products to Finish` field in :guilabel:`Finished Products` tab.
..

If you want to start production, click the button :guilabel:`Confirm Production`, and OpenERP automatically completes the :guilabel:`Products to Consume` field in the :guilabel:`Consumed Products` tab and :guilabel:`Products to Finish` field in :guilabel:`Finished Products` tab.

.. i18n: The information in the :guilabel:`Consumed Products` tab can be changed if:
..

The information in the :guilabel:`Consumed Products` tab can be changed if:

.. i18n: * you want to enter a serial number for raw materials,
.. i18n: 
.. i18n: * you want to change the quantities consumed (lost during production).
..

* you want to enter a serial number for raw materials,

* you want to change the quantities consumed (lost during production).

.. i18n: For traceability, you can set lot numbers on the raw materials used, or on the finished
.. i18n: products.
.. i18n: Note the :guilabel:`Production Lot` and :guilabel:`Pack` numbers.
..

For traceability, you can set lot numbers on the raw materials used, or on the finished
products.
Note the :guilabel:`Production Lot` and :guilabel:`Pack` numbers.

.. i18n: Once the order is confirmed, you should force the reservation of materials
.. i18n: using the :guilabel:`Force Reservation` button. This means that you do not have
.. i18n: to wait for the scheduler to assign and reserve the raw materials from your stock for this
.. i18n: production run. This shortens the procurement process.
..

Once the order is confirmed, you should force the reservation of materials
using the :guilabel:`Force Reservation` button. This means that you do not have
to wait for the scheduler to assign and reserve the raw materials from your stock for this
production run. This shortens the procurement process.

.. i18n: If you do not want to change the priorities, just leave the production order in this state and the scheduler will create a plan based on the priority and your planned date.
..

If you do not want to change the priorities, just leave the production order in this state and the scheduler will create a plan based on the priority and your planned date.

.. i18n: To start the production of products, click :guilabel:`Start Production`. The raw materials are then consumed automatically from stock, which means that the draft ( ``Waiting`` ) movements become ``Done``.
..

To start the production of products, click :guilabel:`Start Production`. The raw materials are then consumed automatically from stock, which means that the draft ( ``Waiting`` ) movements become ``Done``.

.. i18n: Once the production is complete, click :guilabel:`Produce`. The finished products are now moved into stock.
..

Once the production is complete, click :guilabel:`Produce`. The finished products are now moved into stock.

.. i18n: .. Copyright © Open Object Press. All rights reserved.
..

.. Copyright © Open Object Press. All rights reserved.

.. i18n: .. You may take electronic copy of this publication and distribute it if you don't
.. i18n: .. change the content. You can also print a copy to be read by yourself only.
..

.. You may take electronic copy of this publication and distribute it if you don't
.. change the content. You can also print a copy to be read by yourself only.

.. i18n: .. We have contracts with different publishers in different countries to sell and
.. i18n: .. distribute paper or electronic based versions of this book (translated or not)
.. i18n: .. in bookstores. This helps to distribute and promote the OpenERP product. It
.. i18n: .. also helps us to create incentives to pay contributors and authors using author
.. i18n: .. rights of these sales.
..

.. We have contracts with different publishers in different countries to sell and
.. distribute paper or electronic based versions of this book (translated or not)
.. in bookstores. This helps to distribute and promote the OpenERP product. It
.. also helps us to create incentives to pay contributors and authors using author
.. rights of these sales.

.. i18n: .. Due to this, grants to translate, modify or sell this book are strictly
.. i18n: .. forbidden, unless Tiny SPRL (representing Open Object Press) gives you a
.. i18n: .. written authorisation for this.
..

.. Due to this, grants to translate, modify or sell this book are strictly
.. forbidden, unless Tiny SPRL (representing Open Object Press) gives you a
.. written authorisation for this.

.. i18n: .. Many of the designations used by manufacturers and suppliers to distinguish their
.. i18n: .. products are claimed as trademarks. Where those designations appear in this book,
.. i18n: .. and Open Object Press was aware of a trademark claim, the designations have been
.. i18n: .. printed in initial capitals.
..

.. Many of the designations used by manufacturers and suppliers to distinguish their
.. products are claimed as trademarks. Where those designations appear in this book,
.. and Open Object Press was aware of a trademark claim, the designations have been
.. printed in initial capitals.

.. i18n: .. While every precaution has been taken in the preparation of this book, the publisher
.. i18n: .. and the authors assume no responsibility for errors or omissions, or for damages
.. i18n: .. resulting from the use of the information contained herein.
..

.. While every precaution has been taken in the preparation of this book, the publisher
.. and the authors assume no responsibility for errors or omissions, or for damages
.. resulting from the use of the information contained herein.

.. i18n: .. Published by Open Object Press, Grand Rosière, Belgium
..

.. Published by Open Object Press, Grand Rosière, Belgium
