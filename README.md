# Noodle

Here we have a nice little script. Written as an add-on for Google Sheets. 

## What does it do?

It takes an EDI dump file from the [diCentral](https://diwebc.dicentral.com) which contains a whole bunch of lines with order details.
Relevant details are:
  - PO Number
  - Store Number
  - Style name
  - Model Number (sku)
  - Size
  - Quantity
  
noodle transforms this data into a size grid that is broken out by style then by store.

Perhaps screenshots would explain better...

Before:
![before](https://i.imgur.com/cW7UFrh.png)

After:
![after](https://i.imgur.com/LMcy2Qt.png)


## Technologies of Note

This project takes advantage of a lot of new improvements to the google-apps-scripts (GAS) ecosystem
The biggest one is [clasp](https://github.com/google/clasp) which enables local development (with --watch) as well as typescript (which includes ES6) compilation.

I also added the `google-apps-script` type package in order to enable intellisense in vscode
It can be installed via `npm i -S @types/google-apps-script` per this [great guide](https://github.com/google/clasp/blob/master/docs/typescript.md)

If you want to write a google apps scripts do yourself a favor and look into clasp