# isAPIup
Length based API testing and monitoring library




# Usuage:

import isAPIup

#This will create sqlite3 db on current path<br>
obj=isAPIup.create("test")<br>
<br>
#This will insert the url and other parameters<br>
obj.insert("http://localhost:5000/test/a","GET",23,100)<br>
obj.insert("http://localhost:5000/test/b","GET",23,100)<br>
obj.insert("http://localhost:5000/test/c","GET",23,100)<br>
<br>
#insert parameters<br>
#insert(url:str,method:str,working_response_length:int,max_retry:int,headers=None,payload=None)<br>
#url : API url<br>
#method:  GET or POST<br>
#working_response_length: >length for success response<br>
#max_retry: max number or retry on an API<br>
#headers: API Headers<br>
#payload: API Payload<br>
<br>
#This will start scanning the data which is provided above and change the status of running ones<br>
obj.start()<br>
<br>
#This will return the response of live working API<br>
response=obj.execute()<br>
>>> response<br>
<Response [200]><br>
>>> response.text<br>
'{\n  "msg": "working fine"\n}\n'

