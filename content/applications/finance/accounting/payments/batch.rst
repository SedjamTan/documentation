==============
Batch payments
==============

Batch payments act as an organizational tool that groups multiple individual customer or vendor
payments into a single file. Rather than managing transactions one by one, you can consolidate them
to generate a detailed deposit slip or a single electronic payment file. This significantly
simplifies bank :doc:`reconciliation <../bank/reconciliation>`: when a bulk sum appears on your bank
statement, Odoo uses the batch reference to automatically match and reconcile all underlying
payments in a single step.

For customer payments, the feature supports both physical assets, such :doc:`checks <checks>` and
cash, and electronic transfers. You can group daily receipts into one batch to print a bank deposit
slip, ensuring your internal records mirror the lump-sum deposit on your bank statement. On the
vendor side, batch payments streamline bulk electronic transfers. Instead of processing supplier
invoices manually, you can select multiple bills and generate a single outgoing payment file to
upload directly to your banking portal. Because these file formats are region-specific (e.g.,
:doc:`SEPA <sepa_payments>` in Europe, :ref:`NACHA <l10n_us/nacha>` in the U.S., or the global
:ref:`ISO 20022 <accounting/sepa_payments/iso20022>` standard), you should consult your country's
:doc:`fiscal localization <../../fiscal_localizations>` documentation to verify supported formats.

.. seealso::
   - :doc:`../payments`

.. _accounting/batch/configuration:

Configuration
=============

To enable batch payments, open the **Accounting** app, go to :menuselection:`Configuration -->
Settings`, scroll down to the :guilabel:`Customer Payments` section, and enable :guilabel:`Batch
Payments`.

.. note::
   This enables both customer *and* vendor batch payments.

.. tip::
   According to your needs, check that the following apps are installed in the **Apps** app:

   - Batch Payment
   - Account Batch Payment Reconciliation
   - SEPA Credit Transfer
   - SEPA Direct Debit
   - SEPA Payments for Payroll
   - Payment Provider: Sepa Direct Debit
   - NACHA Payments

.. _accounting/batch/creation:

Batch creation
==============

To create customer or vendor batch payments, reproduce the following steps:

#. Make sure all payments to be included in the batch have been :ref:`registered
   <accounting/payments/from-invoice-bill>`.
#. Open the **Accounting** app and go to :menuselection:`Customers --> Batch Payments` or
   :menuselection:`Vendors --> Batch payments` according to the nature of the payment.
#. Click :guilabel:`New`. From here, some configuration is required:

   - :guilabel:`Batch Type`: select whether the money is being transferred to your account
     (:guilabel:`Inbound`) or to somebody else's account (:guilabel:`Outbound`).
   - :guilabel:`Bank`: the bank journal to use for this batch.
   - :guilabel:`Payment Method`: the payment method used for the invoices' payments. Only payments
     matching the payment method selected will appear.
   - :guilabel:`Date`: the batch's creation date
   - :guilabel:`Reference`: the reference of the batch. Leave it empty to generate it automatically.
   - :guilabel:`Add a line`: click it to select the payments to include in the batch.
#. Once all desired payments are included, click :guilabel:`Validate` to finalize the batch.

Alternatively, you can:

#. Make sure all payments to be included in the batch have been :ref:`registered
   <accounting/payments/from-invoice-bill>`.
#. Open the **Accounting** app and go to :menuselection:`Customers --> Payments` or
   :menuselection:`Vendors --> Payments` and select all payments to include in the batch.
#. Click :guilabel:`Create Batch`, *or* :icon:`fa-cog` :guilabel:`(Actions)`, and select
   :guilabel:`Create batch payment`.
#. In the view form, review the selected payments. If any individual payments are missing, click
   :guilabel:`Add a line`, then select the missing payments to include in the batch.
#. Once all desired payments are included, click :guilabel:`Validate` to finalize the batch.

To view existing batch payments, go to :menuselection:`Customers --> Batch Payments` or
:menuselection:`Vendors --> Batch Payments`.

.. note::
   - All payments in a batch *must* use the same payment method.
   - Once validated, no additional payments can be added to a batch. You can delete the batch if
     necessary by clicking :icon:`fa-cog` :guilabel:`(Actions)` and then :icon:`fa-trash-o`
     :guilabel:`(Delete)`.

.. tip::
   - Click :guilabel:`Print` to download a list of the included payments.
   - To filter payments by payment method, click on the :guilabel:`Payment Method` column header
     during the batch payment creation step.


.. _accounting/batch/bank_reconciliation:

Bank reconciliation
===================

Once the bank transactions :doc:`have been created <../bank/transactions>` in your database, you can
:ref:`reconcile them with the batch payment <reconciliation/batch-payments>`.

.. image:: batch/batch-reconciliation.png
   :alt: Reconciling the batch payment with all its transactions

.. note::
   If a specific payment could not be processed by the bank or is missing, remove the line
   corresponding to that payment by using the :icon:`fa-trash-o` (:guilabel:`Delete`) button before
   validating the reconciliation of the batch payment.
