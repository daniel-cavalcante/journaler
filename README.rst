Journaler
=========

*Journaler is a python library for keeping records in an organised way.*

Planning phase: what should it do?
----------------------------------

It should...

#. allow the user to create a journal. Each journal has a corresponding
   directory where its contents are stored.

#. allow the user to read and write logs in a journal.

#. organize the logs by type: same type logs are kept in the same directory.

#. allow the user to retrieve logged info by using any combination of type and
   date parameters, including wild cards.

By these requirements, the directory structure a user created journal should be
similar to 

::

    journaler/
    └── x_journal
        ├── log_a
        ├── log_b
        └── log_c

where x_journal is the name of a journal created by the user and log_k are
illustrative examples of different classes of logs.

On the command line, I expect a command similar to 

    $ journal --read text 1992-04-23

to print on screen all logs of type "text" from day 1992-04-23. For writting,

    $ journal --write text "I just have been born into this world"

to write a text log and save it to a file YYYY-MM-DD.txt inside the directory

    journaler/example_journal/text

Planning phase: possible classes
--------------------------------

All logs should be derived from an abstract base classe called "Log". The Log
class contains only two methods: read and write.

Ideas of classes:

#. TextLog class. It has only two fields: 'content' of type string and
   'created_at' of type datetime. It is the simplest kind of log and I expect a
   lot of other logs to be derived from this class.

#. FinanceLog class. A class o log for the user to register financial records
   of many kinds and retrieved them in a very organized manner. This class
   should have fields like 'location', 'object' and 'value'. Perhaps even more
   details about a purchase, like which card was used in the transaction etc.

#. ReminderLogs.

#. EventLogs.

#. WorkLogs.
