=======
Vietnam
=======

.. _S-Invoice: https://www.sinvoice.vn/

.. _vietnam/configuration:

Configuration
=============

.. _vietnam/configuration/modules:

Modules installation
--------------------

:ref:`Install <general/install>` the following modules to get the latest features of the Vietnamese
localization:

.. list-table::
    :header-rows: 1

    * - Name
      - Technical name
      - Description
    * - :guilabel:`Vientam - Accounting`
      - `l10n_vn`
      - This module includes the default
        :ref:`fiscal localization package <fiscal_localizations/packages>`.
    * - :guilabel:`Vietnam - E-invoicing`
      - `l10n_vn_edi_viettel`
      - This module includes the features required for integation with S-Invoice.
    * - :guilabel:`Vietnam - Accounting Reports`
      - `l10n_vn_reports`
      - This module includes the accounting reports for Vietnam.

.. note::
   When `Vietnam` is selected for a company's :guilabel:`Fiscal Localization`, Odoo automatically
   installs specific modules.

.. _vietnam/configuration/company:

Configure your company
----------------------

To configure your company information, go to the :guilabel:`Contacts` app, search for your company,
and select it. Then configure the following fields:

- :guilabel:`Name`
- :guilabel:`Address`, including the :guilabel:`City`, :guilabel:`State`, :guilabel:`Zip Code`,
  and :guilabel:`Country`.

   - In the :guilabel:`Street` field, enter the street name, number, and any additional address
     information.
   - In the :guilabel:`Street 2` field, enter the neighborhood.

- :guilabel:`Tax ID`: The tax identificaiton number

.. _vietnam/sinvoice:

E-invoice integration with S-Invoice
====================================

S-Invoice_  is an e-invoice service platform provided by Viettel, one of the biggest e-invocie service provider in Vietnam.
Odoo supports integration with S-invoice to submit the invoices generated in Odoo.

.. note::
   The :guilabel:`Vietnam - E-invoicing module` must be installed to submit invoices to S-invoice.

.. _vietnam/sinvoice/setup:

Set-up
------

.. _vietnam/sinvoice/setup/registration:

S-Invoice Registration
~~~~~~~~~~~~~~~~~~~~~~

To send electronic invoices to S-Invoice, you first need to register to the S-Invoice portal to confirm the package, choose
the invoice template and issue a legal notice for the chosen template.

#. Go to S-Invoice_ and :guilabel:`Log in` on the portal.

.. note::
   To create an account, contact :guilabel:`S-Invoice` directly on the portal.

#. Follow the instruction of S-Invoice to choose the invoice template and issue a legal notice of the template chosen.

.. _vietnam/sinvoice/setup/odoo:

Configuration in Odoo
~~~~~~~~~~~~~~~~~~~~~

To connect Odoo database to S-invoice, :guilabel:`Credentials` and :guilabel:`Template invoice` need to be
set first.

#. Go to :menuselection:`Accounting --> Configuration --> Settings`. Under :guilabel:`Vietnamese Integration`,
   connect Odoo database with S-Invoice account using :guilabel:`Username` and :guilabel:`Password`. Set a
   :guilabel:`Default symbol` if needed.

#. Add :guilabel:`S-Invoice Templates` by going to :menuselection:`Accounting --> Configuration --> Templates`.

#. Click :guilabel:`New` to create a new template and add :guilabel:`Template code` and :guilabel:`Template Invoice Type`.

   .. important::
      For the :guilabel:`Template code`, input the code used by Sinvoice excluding any other information in the template name.

      .. example::
         If the invoice template is named `1/001 - Hóa đơn GTGT - ND123`, input `1/001` for :guilabel:`Template code`.


#. Add :guilabel:`Ivnoice Symbols` by selection. New symbol is available for creation directly or under
   :menuselection:`Accounting --> Configuration --> Symbol`.

   .. important::
      Make sure that the :guilabel:`Address` and :guilabel:`Tax ID` of the company contact and the customer's contact is
      filled in properly.

.. _vietnam/sinvoice/workflow:

Workflow
--------

.. _vietnam/sinvoice/workflow/sending:

Create an invoice
~~~~~~~~~~~~~~~~~

Invoices can be sent to MyInvois once they have been confirmed. To do so, follow the
:ref:`invoice sending <accounting/invoice/sending>` steps, and in the :guilabel:`Send` window,
enable the :guilabel:`Send to Sinvoice` option and click :guilabel:`Send & Print`.

.. _vietnam/sinvoice/workflow/sending/status:

Invoice status
**************

In the :guilabel:`SInvoice` tab of the invoice, the :guilabel:`Sinvoice Status` is updated to
:guilabel:`Semt`` when the submission is successful. The :guilabel:`SInvoice Number`,
:guilabel:`Issue Date` and :guilabel:`Secret Code` are also updated.
The same information is available on Sinvoice portal.

.. _vietnam/sinvoice/workflow/adjustment:

Issue a replacement invoice and an adjustment invoice
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Replacement invoice is issued to make an adjustment to the invoice sent that is **not tax declared**, adjustment invoice is issued
for the same that is **already tax declared**.

#. Open the invoice, click :guilabel:`Credit Note`.

#. Fill in the adjustement information indicated below. Click :guilabel:`Reverse and Create Invoice` to issue a replacement invoice,
   click :guilabel:`Revesre` to issue an adjustment invoice.

   .. image:: vietnam/vn-sinvoice-invoice-reverse.png
      :alt: S-Invoice Reverse

#. Upon successful completion of issuing an e-invoice, the :guilabel:`SInvoice Status` of the original invoice replaced is updated to
   :guilabel:`Replaced` upon issuing a replacement invoice and :guilabel:`Adjusted` upon issuing an adjustment invoice.

.. _vietnam/sinvoice/workflow/cancel:

Cancel an Invoice
~~~~~~~~~~~~~~~~~

#. Open the invoice, click :guilabel:`Request Cancel`.

#. Fill in the adjustement information indicated below and click :guilabel:`Request Cancellation`.

   .. image:: vietnam/vn-sinvoice-invoice-cancel.png
      :alt: S-Invoice Request Cancellation

.. _vietnam/qrcode:

Add Vietnamese QR banking codes to invoices
===========================================

Vietnamese QR banking is a payment service platform that allows customers to make instant domestic
payments to individuals and merchants in Vietnamese dong via online and mobile banking.

.. _vietnam/qrcode/set-up:

Set-up
------

.. _vietnam/qrcode/set-up/activate:

Activate QR codes
~~~~~~~~~~~~~~~~~

Go to :menuselection:`Accounting --> Configuration --> Settings`. Under the :guilabel:`Customer
Payments` section, activate the :guilabel:`QR Codes` feature.

.. _vietnam/qrcode/set-up/bank:

Vietnamese QR banking bank account configuration
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Go to :menuselection:`Contacts --> Configuration --> Bank Accounts` and select the bank account for
which you want to activate Vietnamese QR banking. Set the :guilabel:`Bank Identifier Code` on the
bank. Then set the :guilabel:`Proxy Type` and fill in the :guilabel:`Proxy Value` field depending on
the type you chose.

.. important::
   - The account holder's country must be set to `Vietnam` on its contact form.
   - The account holder's city is mandatory.
   - You could also include the invoice number in the QR code by checking the :guilabel:`Include
     Reference` checkbox.

.. image:: vietnam/vn-paynow-bank-setting.png
   :alt: Vietnamese QR banking bank account configuration

.. seealso::
   :doc:`../accounting/bank`

.. _vietnam/qrcode/set-up/journal:

Bank journal configuration
~~~~~~~~~~~~~~~~~~~~~~~~~~

Go to :menuselection:`Accounting --> Configuration --> Journals`, open the bank journal, then fill
out the :guilabel:`Account Number` and :guilabel:`Bank` under the :guilabel:`Journal Entries` tab.

.. image:: vietnam/vn-bank-account-journal-setting.png
   :alt: Bank Account's journal configuration

.. _vietnam/qrcode/workflow:

Workflow
--------

.. _vietnam/qrcode/workflow/issue:

Issue invoices with Vietnamese QR banking QR codes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When creating a new invoice, open the :guilabel:`Other Info` tab and set the :guilabel:`Payment
QR-code` option to *EMV Merchant-Presented QR-code*.

.. image:: vietnam/vn-qr-code-invoice-setting.png
   :alt: Select EMV Merchant-Presented QR-code option

Ensure that the :guilabel:`Recipient Bank` is the one you configured, as Odoo uses this field to
generate the Vietnamese QR banking QR code.
