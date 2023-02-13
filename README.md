# Rejering_API
Gets data  about members of government from their API. Does some simple calculations.

First an API request is sent to "https://data.stortinget.no/eksport/regjering" to get data in an XML format
Then the XML string is deserialized into a XDocument.
The list of members is then read from the document.

Going through each government member their gender, age and id is collected.
Their age is found by subtracting current time by their birthday.

After this the prosses reads an excel document and finds out which members are missing from it.
The excel document is saved as a data table. 
A list of IDs in the excel document is then collected by going through each row and locking at the "ID" column.

There is now a list of IDs gotten from the government API, and a list of IDs gotten by reading the excel document. 
The missing members is found by going through the IDs gotten from the API and checking if they are in the excel list of IDs.
