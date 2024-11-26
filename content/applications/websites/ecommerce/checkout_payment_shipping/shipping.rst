========
Shipping
========

When shopping online, customers can choose their shipping method from the options offered at the
time of :doc:`checkout <../checkout_payment_shipping/checkout>`.

You can integrate with :ref:`external providers <ecommerce/shipping/external-provider>` to handle
deliveries, fetch real-time rates, generate labels, and track shipments, or offer
:ref:`custom shipping options <ecommerce/shipping/custom-method>` like flat-rate shipping, free
shipping, or :doc:`Sendcloud <../../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/sendcloud_shipping>`
carriers.

.. _ecommerce/shipping/external-provider:

External provider integration
=============================

To handle product delivery, you can connect your system to third-party shipping carriers like
:doc:`FedEx <../../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/fedex>`,
:doc:`UPS <../../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/ups_credentials>`,
:doc:`DHL <../../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/dhl_credentials>`,
or local couriers. A shipping connector links your business platform to these providers, automating
communication, tracking, and shipping processes.

To enable a third-party shipping method, go to :menuselection:`Website --> Configuration -->
Settings`, scroll to the :guilabel:`Shipping` section, select the shipping provider(s) you want,
then :ref:`configure <ecommerce/shipping/configure>` them.

.. _ecommerce/shipping/configure:

Configuration
-------------

Once installed, you can configure your shipping methods by going to :menuselection:`Website -->
Configuration --> eCommerce: Shipping Methods`. Here, you find a list of available :guilabel:`Shipping Methods`
along with details such as such the :guilabel:`Provider`, whether the method
:guilabel:`Is Published` on your eCommerce, and more.

Click an existing delivery method to :ref:`configure it <inventory/shipping_receiving/shipping-methods-details>`
and fill out the API credential fields (e.g. API key, password, account number, etc.) in the
:guilabel:`Configuration tab`.

.. _ecommerce/shipping/custom-method:

Custom shipping method
======================

To create a custom shipping method, go to :menuselection:`Website --> Configuration --> eCommerce:
Shipping Methods`, click :guilabel:`New` and fill in the :ref:`details <inventory/shipping_receiving/shipping-methods-details>`.

When you create a custom shipping method and select :ref:`Based on Rules <inventory/shipping/rules>`,
:ref:`Fixed Price <inventory/shipping/fixed>`, or :ref:`Pickup in store <inventory/shipping/pickup>`
in the :guilabel:`Provider` field, the shipping method doesn't involve a specific provider. However,
a provider is required in the following cases:

- **Adding carriers not available by default**: If you wish to use a carrier that is not
  pre-configured in the system, such as DHL via :doc:`Sendcloud <../../../inventory_and_mrp/inventory/shipping_receiving/setup_configuration/sendcloud_shipping>`,
  you need to create a new shipping method manually to enable its usage.

- **Customizing existing shipping methods**: If you want to modify an existing shipping method to
  apply different rules — for example, offering free shipping for orders above 100 euros — you need
  to configure this as a new method.

- **Creating website-specific shipping options**: To create a shipping method tailored to a specific
  website, navigate to :menuselection:`Website --> Configuration --> Settings --> Shipping Methods`.
  Select the desired shipping method and specify the website you want it restricted to by setting it
  in the :guilabel:`Website` field. If you want the shipping method to be available on all websites,
  leave the field empty.
