=================================
Customer and vendor bank accounts
=================================

Odoo stores your :doc:`contacts' <../../../essentials/contacts>` banking details on their profile,
automatically filling out banking-related fields for all Odoo operations related to these contacts.
By default, it also protects you from :ref:`phishing scams
<accounting/customer-vendor-bank-accounts/phishing>` by preventing any outgoing wire transfer until
the contact's bank account is marked as 'trusted'.

.. seealso::
   - :doc:`sepa_payments`

.. _accounting/customer-vendor-bank-accounts/configuration:

Configuration
=============

To link a bank account to a contact, open an Odoo app with access to contacts (e.g., **Accounting**
or **Contacts** app), choose a contact, then go to the :guilabel:`Accounting` tab. In
:guilabel:`Bank Accounts`, click :guilabel:`Add a line` and fill in :guilabel:`Account Number`,
:guilabel:`Bank`, :guilabel:`Account Holder Name`, :guilabel:`Account Holder`, and, if needed,
:guilabel:`Company` and :guilabel:`Currency`. Toggle :guilabel:`Send Money` to mark the account as
'trusted'.

.. note::
   By default, all accounts start as 'untrusted'.

.. _accounting/customer-vendor-bank-accounts/phishing:

Phishing attacks
================

A **phishing attack** is an online scam designed to trick individuals or companies into giving away
sensitive information or money by sending out fraudulent communication. Fraudsters pretend to be
legitimate companies and may use partial information to give credibility to their requests.

There are several types of phishing attacks, including **invoice fraud**. In this case, the
fraudster pretends to be a genuine supplier following up on unpaid bills or sending a new invoice,
but with different payment information than usual and with fake contact details.

To protect yourself from these types of phishing attacks, remain vigilant when you receive
unexpected invoices or payment requests.

.. important::
   In case of doubt, **we recommend contacting the vendor by phone**. Make sure to call an official
   phone number by searching yourself, as the URLs, email addresses, and phone numbers written in
   the communication you received may be fake.

Elements to check
-----------------

There are several elements you can check by yourself when you receive an outgoing payment request to
a new account:

Communication style
  Fraudulent emails and invoices often use a different communication style, such as **different
  wording**, and may include **spelling and grammatical mistakes**. Examine and **compare** them
  with previous ones that you know to be authentic (e.g., payment instructions, language, company
  logo, etc.).*

Urgency
  Invoice frauds often use **urgent or threatening language** and change the **payment deadline**.
  Check if you really received a late payment reminder previously.

Type of account
  A company is unlikely to replace a bank account with a **money transfer service**.

Email and links domain names
  Double-check the **email address domain** (`example@domain.com`). However, be wary that fraudsters
  can make their email addresses look genuine or even hack email addresses from your vendor's
  employees or even someone within your own organization.

  Hover over the links in your email and check that the URLs they redirect to are genuine. Your
  internet browser usually displays the link's target at the bottom left of the window.
