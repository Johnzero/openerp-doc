
.. module:: point_of_sale_extension
    :synopsis: Point Of Sale Extension 
    :noindex:
.. 

.. raw:: html

      <br />
    <link rel="stylesheet" href="../_static/hide_objects_in_sidebar.css" type="text/css" />

.. tip:: This module is part of the OpenERP software, the leading Open Source 
  enterprise management system. If you want to discover OpenERP, check our 
  `screencasts <http://openerp.tv>`_ or download 
  `OpenERP <http://openerp.com>`_ directly.

.. raw:: html

    <div class="js-kit-rating" title="" permalink="" standalone="yes" path="/point_of_sale_extension"></div>
    <script src="http://js-kit.com/ratings.js"></script>

Point Of Sale Extension (*point_of_sale_extension*)
===================================================
:Module: point_of_sale_extension
:Name: Point Of Sale Extension
:Version: 5.0.1.0
:Author: Zikzakmedia SL
:Directory: point_of_sale_extension
:Web: http://www.zikzakmedia.com
:Official module: no
:Quality certified: no

Description
-----------

::

  * Only it allows delete draft or cancelled POS orders and POS order lines.
  * If POS order has a partner, the partner is stored in:
      - The stock.picking created by the pos order.
      - The account.move.line created by the pos order.
  * POS orders with amount_total==0 no creates account moves (it gives error).
  * Shows the payment type (journal) in the payments list in the second tab of the POS.
  * The journals used to pay with the POS can be chosen (in the configuration tab of the company: Administration / Users / Companies).
  * Product prices with or without taxes included (select in the configuration tab of the company).
  * Shows a warning in the payment wizard (but you can continue) if:
      - A product added in the POS order has already been requested by the partner (the partner has a sale order with this product), so the user can decide if is better to do a POS order from a sale order.
      - There is not enough virtual stock in any of the products.
    These two warnings can be activated/deactivated (in the configuration tab of the company).
  * List and search POS order lines by number of order, partner and state.
  * If product_visible_discount module is installed and visible discount field in price list is checked, computes discounts in point of sale order lines.

Download links
--------------

You can download this module as a zip file in the following version:

(No download links available)


Dependencies
------------

 * :mod:`point_of_sale`

Reports
-------

None


Menus
-------


None


Views
-----

 * \* INHERIT res.company.pos.config (form)
 * \* INHERIT pos.order.form.ext1 (form)
 * \* INHERIT pos.order.form.ext2 (form)
 * \* INHERIT pos.order.form.ext3 (form)
 * \* INHERIT pos.order.form.ext4 (form)
 * \* INHERIT pos.order.form.ext5 (form)
 * \* INHERIT pos.order.form.ext6 (form)
 * \* INHERIT pos.order.form.ext7 (form)
 * \* INHERIT pos.order.form.ext8 (form)
 * \* INHERIT Sales ext1 (tree)
 * \* INHERIT Sale lines ext1 (tree)
 * \* INHERIT Sale lines ext2 (tree)
 * \* INHERIT Sale lines ext3 (tree)


Objects
-------

Object: Change path to rml file to get a better POS receipt (pos.report.change)
###############################################################################
