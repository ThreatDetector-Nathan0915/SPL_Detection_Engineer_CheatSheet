rename
**Description:** Renaming a field will transform the field name into the defined name. This will transform the fields name unlike an eval of a field into a new field which will leave the orginal and create a new one. This will rename the orginal and for the rest of the search you will need to use the new name.

**Uses:** Say you have a query that is taking fields from multiple indexes. And in those fields there is the same value, which you are trying to correlate. However, the field names are differnt, example  user, UID, username, ect you can use a rename to rename the fields so they can be correlated together. This is very helpfull for field normalization.

Example Usage 1 rename:
```spl
(greater splunk search)
| rename user as UID
```
Example Usage 2 rename:
```spl
(greater splunk search)
| rename user as UID, username as UID
```
---
regex
**Description:** Defines a pattern that should match a regular expression. Regular expresion is very powerfull, and can be used to precilisly match patterns that otherwise would be impossible to express in regular splunk search terms.

**Uses:** Lets say I am looking for a malicous commandline where the threat actor will be employing obfuscation. A normal splunk search you can define a field=x, field=*x* or you can search just for x (via token) but lets say x will pop up with y, and there are extra characters sprinkled in that break the token for splunk. Also puting wild cards between tokens in Splunk results in terrible search performance example field=*x*y this will aslo return inconsistent results. Never fear regex is here :)

Example Usage (this will search for string 1 and 2 sequentially regex is a massive area that I will break down in a different guide):
```spl
(greater splunk search)
| regex field="(?is)string1.*string2"
```
---
rex
**Description:** The rex is one of my all time personal top favorites. You can use it to extract value from a field into a new field or several new fields. This can be very usefull if for instance you are creating a detection and the regex match is protially in mulple fields. With a standard regex you can only match on one field but with rex you could extract muliple vlaues into a single field, and match of that one field working around the regex limiation with rex. Rex is also field aware so if a field has multple values you would like to become fields of thier own you can write the regex to account for that.

**Uses:**
Example (Usage matching on multple fields returning only positive hits):
```spl
(greater splunk search)
| rex field=commandline "(?<IOAs>bad_pattern1.*badpattern2)"
| rex field=commandhistory "(?<IOAs>bad_pattern1.*badpattern2)"
| rex field=scriptcontent "(?<IOAs>bad_pattern1.*badpattern2)"
| where isnotnull(IOAs)
```
---
rex mode=sed
**Description:**
**Uses:**
**Example Usage:**
---
where
**Description:**
**Uses:**
**Example Usage:**
---
lookup
**Description:**
**Uses:**
**Example Usage:**
---
isnull/isnotnull
**Description:**
**Uses:**
**Example Usage:**
---
index_earliest
**Description:**
**Uses:**
**Example Usage:**
---
dc
**Description:**
**Uses:**
**Example Usage:**
---
stats
**Description:**
**Uses:**
**Example Usage:**
---
values
**Description:**
**Uses:**
**Example Usage:**
---
bin
**Description:**
**Uses:**
**Example Usage:**
---
lower/upper
**Description:**
**Uses:**
**Example Usage:**
---
IN
**Description:**
**Uses:**
**Example Usage:**
---
table
**Description:**
**Uses:**
**Example Usage:**
---
coalesc
**Description:**
**Uses:**
**Example Usage:**
---
mvmap
**Description:**
**Uses:**
**Example Usage:**
---
makemv
**Description:**
**Uses:**
**Example Usage:**
---
map
**Description:**
**Uses:**
**Example Usage:**
---
TERM
**Description:**
**Uses:**
**Example Usage:**
---
head/tail
**Description:**
**Uses:**
**Example Usage:**
---
rex mode=sed 
**Description:**
**Uses:**
**Example Usage:**
---
transaction
**Description:**
**Uses:**
**Example Usage:**
---
strftime
**Description:**
**Uses:**
**Example Usage:**
---
join
**Description:**
**Uses:**
**Example Usage:**
---
convert ctime
**Description:**
**Uses:**
**Example Usage:**
---
fillnull
**Description:**
**Uses:**
**Example Usage:**
---
strcat
**Description:**
**Uses:**
**Example Usage:**
---
case
**Description:**
**Uses:**
**Example Usage:**
---
if
**Description:**
**Uses:**
**Example Usage:**
---
match vs like
**Description:**
**Uses:**
**Example Usage:**
---
hex decode
**Description:**
**Uses:**
**Example Usage:**
---
append info to lookup
**Description:**
**Uses:**
**Example Usage:**
---
collect
**Description:**
**Uses:**
**Example Usage:**
---
append (subsearch)
**Description:**
**Uses:**
**Example Usage:**
---
iplocation
**Description:**
**Uses:**
**Example Usage:**
---
fieldsummary
**Description:**
**Uses:**
**Example Usage:**
---
metadata
**Description:**
**Uses:**
**Example Usage:**
---