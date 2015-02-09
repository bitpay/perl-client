BitPay Perl Client
==================
Business::BitPay - BitPay API

## SYNOPSIS

    use Business::BitPay;
    my $bitpay = Business::BitPay->new($api_key);

    # create new invoice
    $invoice = $bitpay->create_invoice(price => 10, currency => 'USD');

    # get invoice data
    $invoice = $bitpay->get_invoice($invoice->{id});

## DESCRIPTION
BitPay API documentation contents full description of API methods: https://bitpay.com/help-api.

### new
```perl
    my $bitpay = Business::BitPay->new($api_key);
```
Construct Business::BitPay object.

### create_invoice
```perl
    my $invoice = $bitpay->create_invoice(price => 10, currency => 'USD');
```
Creates new invoice. This method will croak in case of error. Full list of
fields and their description can be found in C<Creating an Invoice> section of
BitPay API documentation.

Returns hashref representing of the invoice object. Description can be found in
C<BitPay Server Response> section of the BitPay API documentation.

### get_invoice
```perl
    my $invoice = $bitpay->get_invoice($invoice_id);
```
Returns invoice hashref or croak if error occurred. Returned invoice object has
exactly the same format as that which is returned when creating an invoice.

## SEE ALSO
https://bitpay.com/downloads/bitpayApi.pdf

## AUTHOR
Sergey Zasenko, undef@cpan.org

## COPYRIGHT AND LICENSE

Copyright (C) 2013, Sergey Zasenko.

This program is free software, you can redistribute it and/or modify it under
the same terms as Perl 5.10.
