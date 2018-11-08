# Noodle

Here we have a nice little script, written as an add-on for Google Sheets. 

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
![before](https://camo.githubusercontent.com/e9019b612d72d78fbe21c47679befd4627097946/68747470733a2f2f692e696d6775722e636f6d2f635737554672682e706e67)

After:
![after](https://i.imgur.com/LMcy2Qt.png)


## Technologies of Note

This project takes advantage of a lot of new improvements to the google-apps-scripts (GAS) ecosystem
The biggest one is [clasp](https://github.com/google/clasp) which enables local development (with --watch) as well as typescript (which includes ES6) compilation.

I also added the `google-apps-script` type package in order to enable intellisense in vscode
It can be installed via `npm i -S @types/google-apps-script` per this [great guide](https://github.com/google/clasp/blob/master/docs/typescript.md)

If you want to write a google apps script do yourself a favor and look into [clasp](https://github.com/google/clasp)

## How to use

If you somehow have a use for this script, you can add it to one of your google sheets by the folowing steps:
  1. Clone the project by running `git clone git@github.com:joesasson/noodle.git` from the directory you want the project to be in
  2. Install clasp by running `sudo npm i @google/clasp -g` - (If you have problems, check [here](https://github.com/google/clasp/#install))
  3. Once installed, run clasp login which will open a browser window asking you to authorize clasp
  4. Authorize via the browser, and paste token into the terminal
  5. Run `clasp create` in order to start a new project
  6. Run `clasp push` in order to upload files to google drive (You can also use `clasp push --watch` to push all changes that you make automatically)
  7. Open the project using `clasp open` - You will see the compiled file
  8. From the "Run" Menu click "Test as add-on..." and select the document that you would like to use the script with
  9. Open the document (you must be viewing the sheet with the dump) and click on the menu item Add-ons > noodle > Create Size Grid By Store
  10. Profit!!