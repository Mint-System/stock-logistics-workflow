==================================
Stock Customer Deposit Sale Margin
==================================

.. 
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
   !! This file is generated by oca-gen-addon-readme !!
   !! changes will be overwritten.                   !!
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
   !! source digest: sha256:1be08bdb0929dfe48f0adb39b58d94045898b87468e12c52b132c54f082af39d
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

.. |badge1| image:: https://img.shields.io/badge/maturity-Alpha-red.png
    :target: https://odoo-community.org/page/development-status
    :alt: Alpha
.. |badge2| image:: https://img.shields.io/badge/licence-LGPL--3-blue.png
    :target: http://www.gnu.org/licenses/lgpl-3.0-standalone.html
    :alt: License: LGPL-3
.. |badge3| image:: https://img.shields.io/badge/github-OCA%2Fstock--logistics--workflow-lightgray.png?logo=github
    :target: https://github.com/OCA/stock-logistics-workflow/tree/16.0/stock_customer_deposit_sale_margin
    :alt: OCA/stock-logistics-workflow
.. |badge4| image:: https://img.shields.io/badge/weblate-Translate%20me-F47D42.png
    :target: https://translation.odoo-community.org/projects/stock-logistics-workflow-16-0/stock-logistics-workflow-16-0-stock_customer_deposit_sale_margin
    :alt: Translate me on Weblate
.. |badge5| image:: https://img.shields.io/badge/runboat-Try%20me-875A7B.png
    :target: https://runboat.odoo-community.org/builds?repo=OCA/stock-logistics-workflow&target_branch=16.0
    :alt: Try me on Runboat

|badge1| |badge2| |badge3| |badge4| |badge5|

This module extends the functionality of the consignment stock to
support customer deposits and set cost in sale order line to zero when
making another sale order to deliver some previously consigned customer
deposit.

.. IMPORTANT::
   This is an alpha version, the data model and design can change at any time without warning.
   Only for development or testing purpose, do not use in production.
   `More details on development status <https://odoo-community.org/page/development-status>`_

**Table of contents**

.. contents::
   :local:

Use Cases / Context
===================

This module was created to make sure that the cost on a sale order line
is zero when delivering from customer deposits. This is needed because
the purchase price already accounts for the customer deposit in the sale
order. Without this module, the cost would be counted twice in the
accounting.

Usage
=====

To use this module, you need to:

Create Customer deposits:

1.  Go to Sales > Quotations.
2.  Create new quotation to the desired customer.
3.  Activate **customer deposit** in quotation.
4.  Add storable product in order lines.
5.  Add quantity you will keep as a deposit.
6.  *Confirm* quotation.
7.  Sale is now ready for invoicing.
8.  A picking will be created. This picking is an operation Customer
    Deposit and it's **internal** operation.
9.  Click on smart button with delivery.
10. Set quantity done in operations or click on **Set Quantities**.
11. Update location destination if it's necessary in operations
    detailed.
12. Click on **Validate**.

Deliver customer deposits:

1.  Go to Sales > Quotation.
2.  Create a new quotation.
3.  Select a customer who has a deposit in your warehouse.
4.  In page Other Info choose warehouse where deposit is located. (Only
    if multi-warehouse is activated)
5.  Smart button **Deposits** with deposits is displayed if the customer
    has deposits in the chosen warehouse.
6.  Add line with product in deposit.
7.  Purchase price is set to zero.
8.  As a product in deposit, a button **Customer deposit** will appear.
    If you do not have enough in deposit, button will be grey. If you
    click on the button **Customer deposit**, you can view the deposits
    for that product.
9.  You will only be able to confirm the order if you use less quantity
    than you have in the deposit.
10. If you try to confirm the order with more quantity than you have in
    deposit, a validation error will show.

Bug Tracker
===========

Bugs are tracked on `GitHub Issues <https://github.com/OCA/stock-logistics-workflow/issues>`_.
In case of trouble, please check there if your issue has already been reported.
If you spotted it first, help us to smash it by providing a detailed and welcomed
`feedback <https://github.com/OCA/stock-logistics-workflow/issues/new?body=module:%20stock_customer_deposit_sale_margin%0Aversion:%2016.0%0A%0A**Steps%20to%20reproduce**%0A-%20...%0A%0A**Current%20behavior**%0A%0A**Expected%20behavior**>`_.

Do not contact contributors directly about support or help with technical issues.

Credits
=======

Authors
-------

* Moduon

Contributors
------------

-  Emilio Pascual (`Moduon <https://www.moduon.team/>`__)
-  Eduardo de Miguel (`Moduon <https://www.moduon.team/>`__)

Maintainers
-----------

This module is maintained by the OCA.

.. image:: https://odoo-community.org/logo.png
   :alt: Odoo Community Association
   :target: https://odoo-community.org

OCA, or the Odoo Community Association, is a nonprofit organization whose
mission is to support the collaborative development of Odoo features and
promote its widespread use.

.. |maintainer-EmilioPascual| image:: https://github.com/EmilioPascual.png?size=40px
    :target: https://github.com/EmilioPascual
    :alt: EmilioPascual
.. |maintainer-rafaelbn| image:: https://github.com/rafaelbn.png?size=40px
    :target: https://github.com/rafaelbn
    :alt: rafaelbn

Current `maintainers <https://odoo-community.org/page/maintainer-role>`__:

|maintainer-EmilioPascual| |maintainer-rafaelbn| 

This module is part of the `OCA/stock-logistics-workflow <https://github.com/OCA/stock-logistics-workflow/tree/16.0/stock_customer_deposit_sale_margin>`_ project on GitHub.

You are welcome to contribute. To learn how please visit https://odoo-community.org/page/Contribute.
