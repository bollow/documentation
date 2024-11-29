==============
Order handling
==============

In Odoo's eCommerce workflow, each purchase creates key documents: a
:ref:`Sales orders <ecommerce/handling/sales>` upon order confirmation, a
:ref:`Delivery orders <ecommerce/handling/delivery>` for handling picking, packaging, and shipping, and an
:ref:`Invoices <ecommerce/handling/legal>` sent to the customer as the final step.

.. _ecommerce/handling/sales:

Sales orders
============

When a customer confirms an online purchase, a Sales Order is automatically created. Sales Order are
available in :menuselection:`Website --> eCommerce --> Orders: Orders`, and click on a SO to view
its information.

.. tip::

   You can assign a sales team or salesperson to manage your online orders by navigating to
   :menuselection:`Website --> Configuration --> Settings`. In the
   :guilabel:`Shop - Checkout Process` section, go to :guilabel:`Assignment` and select the desired
   :guilabel:`Sales Team` or :guilabel:`Salesperson`.

Payment status
--------------

In a Sales Order, the status bar lets you know the payment status:

- **Quotation**: a new product is added to the cart, but the customer has not gone through the
  checkout process yet;
- **Quotation sent**: the customer has gone through the checkout process and confirmed the order,
  but the payment is not yet confirmed;
- **Sales Order**: the customer has completed the checkout process, confirmed the order, and the
  payment is received.

Abandoned cart
--------------

An **abandoned cart** represents an order for which the customer did **not finish** the checkout
confirmation process.
Abandoned carts are available by going to :menuselection:`Website --> eCommerce --> Orders: Abandoned
Carts`.

You can automate the sending of email reminders by going to :menuselection:`Website -->
Configuration --> Settings`. Go to the :guilabel:`Email & Marketing` section to enable
:guilabel:`Automatically send abandoned checkout emails`. Once enabled, you can set the time lapse
after the email is sent and customize the email template.

.. note::
   For abandoned cart emails, the customer must either have entered their contact details during the
   checkout process; or be logged-in when they added the product to their cart.

.. _ecommerce/handling/delivery:

Delivery orders
===============

Once a quotation has been confirmed, a delivery order is automatically created to process the
delivery. From your sales order, click the :guilabel:`Delivery` button to access the delivery order,
or go to :menuselection:`Inventory --> Operations --> Deliveries`, go to the
:guilabel:`Source Document` column, and select your sales order.

Packing eCommerce orders usually requires picking the product, preparing the packaging, printing the
shipping label(s), and shipping to the customer. Depending on the number of orders, strategies, or
resources, those steps can be considered as one or multiple actions in Odoo.

.. tip::
   You can send an automatic confirmation email when delivery orders are completed by enabling the
   feature in :menuselection:`Inventory --> Configuration --> Settings`, scrolling to the
   :guilabel:`Shipping` section, and ticking the :guilabel:`Email Confirmation` box.

.. note::
   If customers are allowed to pay when picking up their order in stores or by wire transfer, the
   quotation is **not** confirmed and the stock is **not** reserved. Orders must be confirmed
   manually to reserve products in stock.

.. seealso::
   - :doc:`../../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/invoicing`
   - :doc:`../../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/labels`
   - :doc:`../../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/multipack`

Returns and refunds
-------------------

Customers can easily return products through their portal by navigating to :guilabel:`My Orders`
section, selecting the relevant order, and clicking :guilabel:`Return`. A return document is then
generated to include in the parcel.

.. Note::
   - Depending on the return strategy or product type, it may not be possible to return products.
   - Full refunds can be sent to customers directly from within the order interface. First, a
     refund-compatible payment provider needs to be enabled.

.. seealso::
   - :doc:`/applications/sales/sales/products_prices/returns`
   - :doc:`/applications/services/helpdesk/advanced/after_sales`
   - :doc:`/applications/finance/payment_providers`

.. _ecommerce/handling/legal:

Invoice
=======

The final step in an e-commerce order is to generate the invoice.

For B2B transactions, invoices are typically created automatically, while in B2C, they are
generated upon customer request.

This process can be fully automated upon online payment confirmation. To enable automatic invoicing,
navigate to :menuselection:`Website --> Configuration --> Settings` and activate the
:guilabel:`Automatic Invoice` option in the :guilabel:`Invoicing` section.
