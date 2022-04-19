# isAPIup
Length based API testing and monitoring library




Usuage:

import isAPIup

#This will create sqlite3 db on current path
obj=isAPIup.create("test")

#This will insert the url and other parameters
obj.insert("http://localhost:5000/test/a","GET",23,100)
obj.insert("http://localhost:5000/test/b","GET",23,100)
obj.insert("http://localhost:5000/test/c","GET",23,100)

#insert parameters
#insert(url:str,method:str,working_response_length:int,max_retry:int,headers=None,payload=None)
#url : API url
#method:  GET or POST
#working_response_length: >length for success response
#max_retry: max number or retry on an API
#headers: API Headers
#payload: API Payload

#This will start scanning the data which is provided above and change the status of running ones
obj.start()

#This will return the response of live working API
response=obj.execute()
>>> response
<Response [200]>
>>> response.text
'{\n  "msg": "working fine"\n}\n'

