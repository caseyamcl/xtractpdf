xtractpdf
=========

## Introduction

Scientific information tends to be locked up in PDF documents, which is an inadequate mechanism
for modern scientific information sharing.  PDFs are not structured, and therefore are difficult
to search and classify.

XtractPDF is a tool for extracting information from PDF documents in a human-assisted way.
The tool automatically attempts to extract and classify content into structured data, but it
also provides a handy interface for humans to clean up and perfect the data.  Documents can then
be exported to JATS-XML (http://dtd.nlm.nih.gov).

XtractPDF currently acts as a client to the PDFX (<http://pdfx.cs.man.ac.uk>)
webservices API.  However, XtractPDF can be extended to support other libraries and APIs.


## Requirements (in recommended order of install):

- Apache2 (`sudo apt-get install apache2`) or NGINX
    - Apache2 Rewrite Module (`sudo a2enmod rewrite`)

- PHP 5.3+ with PEAR (`sudo apt-get install php5 php-pear`)

- PHP Mongo PECL Extension (sudo pecl install mongo)
    - NOTE: After you install this package, you will most likely need to add `extension=mongo.so`
      to your `php.ini` file.

- MongoDB (`sudo apt-get install mongodb`)

- Composer (<http://getcomposer.org/doc/00-intro.md#globally>)

## Installation:

Before proceeding: verify that all requirements mentioned in the previous section have been satisfied.

1. If you have Git installed, you can simply run "git clone https://github.com/idiginfo/xtractpdf.git".
   Otherwise you can download the entire zip package and unpack all the files into a directory of your choosing.

2. In your newly placed XtractPDF directory, you must have the log and uploads directory set with read and write permissions 
   for everybody in order for XtractPDF to process uploaded files and to write logs.

3. Change directory to the XtractPDF working directory, then change directory to app.  Run "composer install".  If all of 
   your dependencies are configured properly, Composer will download all required packages necessary to run XtractPDF.  Wait
   until Composer finishes installing all packages before proceeding.

4. Copy config/config.yml.dist to config/config.yml and verify that all settings match your environment's requirements.

5. You are ready to run the app.  On your web browser navigate to the URL of your freshly installed XtractPDF.


## Technologies

We built XtractPDF entirely on open source technologies:

* PHP Silex Framework
* Monolog
* Guzzle
* MongoDB and Doctrine ODM
* Jquery
* KnockoutJS
* PDFX
* Jquery Autosize
* Jquery Form
* Prettify
* Twitter Bootstrap
* Fontawesome

## Author

XtractPDF was written by Casey McLaughlin (http://caseymclaughlin.com) and is actively maintained 
by Mike Wabiszewski (http://wabice.com) at the iDigInfo Institute (http://idiginfo.org) at Florida 
State University (http://fsu.edu) for work on projects related to the Jailbreaking the PDF 
(http://pdfjailbreak.com) collaboration.
