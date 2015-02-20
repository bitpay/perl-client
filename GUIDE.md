# Using the BitPay Perl Client Library
## Prerequisites
You must have a BitPay merchant account to use this library.  It's free to [sign-up for a BitPay merchant account](https://bitpay.com/start).

Once you have a BitPay merchant account, you will need [a working BitPay Access Token](/api/getting-access.html) – this can be done either [via the library](#pairing) or manually in [the BitPay Dashboard](https://bitpay.com/tokens).

## Quick Start
```perl
use Business::BitPay;
my $bitpay = Business::BitPay->new($api_key);

# create new invoice
$invoice = $bitpay->create_invoice(price => 10, currency => 'USD');

# get invoice data
$invoice = $bitpay->get_invoice($invoice->{id});
```

### New Object Creation
```perl
my $bitpay = Business::BitPay->new($api_key);
```
Construct Business::BitPay object.

### Creating an Invoice
```perl
my $invoice = $bitpay->create_invoice(price => 10, currency => 'USD');
```
Creates new invoice. This method will croak in case of error. Full list of
fields and their description can be found in C<Creating an Invoice> section of
BitPay API documentation.

Returns hashref representing of the invoice object. Description can be found in
C<BitPay Server Response> section of the BitPay API documentation.

### Retrieving an Invoice
```perl
my $invoice = $bitpay->get_invoice($invoice_id);
```
Returns invoice hashref or croak if error occurred. Returned invoice object has
exactly the same format as that which is returned when creating an invoice.

## SEE ALSO
https://bitpay.com/downloads/bitpayApi.pdf
