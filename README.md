CommonRegexDart
===========

This is a port of CommonRegex by Author Madison May (https://github.com/madisonmay)

Find all times, dates, links, phone numbers, emails, ip addresses, prices, hex colors, and credit card numbers in a string. 
We did the hard work so you don't have to.


Installation
-------
Once you have added a dependency in your pubspec.yaml, you'll need to import the library like so:
```
import 'package:common_regex/common_regex.dart'
```


Usage
------
```dart
main() {
    CommonRegex find = new CommonRegex(text: '''
       John, please get that article on www.linkedin.com to
       me by 5:00PM on Jan 9th 2012. 4:00 would be ideal, 
       actually. If you have any questions, you can reach my 
       associate at (012)-345-6789 or associative@mail.com.
       I'll be on UK during the whole week on a J.R.R. Tolkien convention.
       ''');
        
        print(find.dates);   
        print(find.times);
        print(find.links);    
        print(find.emails); 
        print(find.acronyms);
    }
```

returns:

```
[Jan 9th 2012]
[5:00, 4:00]
[www.linkedin.com]
[associative@mail.com]
[UK, J.R.R.]
``` 


Alternatively, you can generate a single CommonRegex instance and use it to parse multiple segments of text.

```dart
    CommonRegex find = new CommonRegex();
    print(find.getTimes (text: 'The time is 1:00; 1 hour away: 2:00!')); 
    print(find.getPhones(text: 'Give us a call: (555) 555-5555,'
        + ' or 555-555-5555. If local: 555-5555')); 
    print(find.getIPv4 (text: 'Valid IPs: 192.168.0.1;192.168.0.2;'
        + ' Invalid IP: 267.277.234.234')); 
```

returns:

```
[1:00, 2:00]
[(555) 555-5555, 555-555-5555, 555-5555]
[192.168.0.1, 192.168.0.2]
```
    
    
Please note that this library is currently English/US specific.


Supported Methods/Attributes
-----------------------------
  - obj.dates, obj.getDates()
  - obj.times, obj.getTimes()
  - obj.phones, obj.getPhones()
  - obj.links, obj.getLinks()
  - obj.emails, obj.getEmails()
  - obj.IPv4, obj.getIPv4()
  - obj.IPv6, obj.getIPv6()
  - obj.hexColors, obj.getHexColors()
  - obj.money, obj.getMoney()
  - obj.percentages, obj.getPercentages()
  - obj.creditCards, obj.creditCards()
  - obj.addresses, obj.getAddresses()


CommonRegex for other Languages:
----------------------------------------
CommonRegex for Python (https://github.com/madisonmay/CommonRegex)

CommonRegexJS (https://github.com/talyssonoc/CommonRegexJS)

CommonRegexScala (https://github.com/everpeace/CommonRegexScala)    

CommonRegexJava (https://github.com/talyssonoc/CommonRegexJava)

CommonRegexCobra (https://github.com/PurityLake/CommonRegex-Cobra)