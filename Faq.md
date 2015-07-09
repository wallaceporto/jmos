# Frequently Asked Questions #

## General ##

#### What is jMOS? ####
jMOS is an easy to use, open source library for working with Newsroom Computer Systems (NCS) and Media Object Servers (MOS) on the Java platform using the fastest processors engines for XML like SAX, JAXP and StAX.

#### What is the Apache license? ####
We use an Apache open source license. In practice this means that you can do almost anything you want with the code, including its use in commercial software.

#### What do I need to add to my CLASSPATH? ####
The jMOS.jar only contains the jMOS classes, you'll have to include the SAX classes and the SAX parser of your choice to your CLASSPATH, you also have to include the StAX, Logger and ara-utils.jar to your CLASSPATH.

#### How to report a bug? ####
The tracker helps to keep all the bug reports in one place. Go through the following steps when reporting a new bug:
  1. Ask yourself is it really a bug. Maybe it's rather a misconfiguration or a hardware failure etc. Double-check that.
  1. Search existing bug reports for similar problems. If it's already there, just post another comment, instead of adding a similar report.
  1. If you have not found an existing report on your problem, consider adding a new bug report.
  1. Choose an informative subject line.
  1. Describe the problem, trying to provide enough information to let a tester reproduce the bug.

#### How to submitting your patch? ####
Patches should be submitted via the issue tracker. Create a bug report or feature request, attach your patch using the file upload form.

## MOS Protocol ##

#### What profiles are supported? ####
Profile 0 and 1.

## Using jMOS ##
#### How to change the default SAX parse? ####
Change the javax.xml.parsers.SAXParserFactory system property before call any static method of Server class.
  * Sample 1:
    * For Crimson xml parsers: System.setProperty("javax.xml.parsers.SAXParserFactory", "org.apache.crimson.jaxp.SAXParserFactoryImpl");
    * For Xerces xml parsers: System.setProperty("javax.xml.parsers.SAXParserFactory", "org.apache.xerces.jaxp.SAXParserFactoryImpl");
  * Sample 2:
    * For Crimson xml parsers: javac -Djavax.xml.parsers.SAXParserFactory=org.apache.crimson.jaxp.SAXParserFactoryImpl
    * For Xerces xml parsers: javac -Djavax.xml.parsers.SAXParserFactory=org.apache.xerces.jaxp.SAXParserFactoryImpl

#### How to change the default StAX writer? ####
Change the javax.xml.stream.XMLOutputFactory system property before call any static method of Server class.
  * Sample 1:
    * For Bea xml parsers: System.setProperty("javax.xml.stream.XMLOutputFactory", "com.bea.xml.stream.MXParserFactory");
    * For WebLogic xml parsers: System.setProperty("javax.xml.stream.XMLOutputFactory", "weblogic.xml.stax.XMLStreamOutputFactory");
  * Sample 2:
    * For Bea xml parsers: javac -Djavax.xml.stream.XMLOutputFactory=com.bea.xml.stream.MXParserFactory
    * For WebLogic xml parsers: javac -Djavax.xml.stream.XMLOutputFactory=weblogic.xml.stax.XMLStreamOutputFactory