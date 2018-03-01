
# Software Engineering Course project template

## Setup dev environment
* Grab Ubuntu 16.04 based VM
* Clone projects
```
  > cd ~
  > mkdir projects
  > cd projects
  > git clone https://github.com/swe-course/saas-template.git
```
* Prepare local env configuration files
```
  > cd saas-template
  > cp .env.template .env
  > cp settings.xml.template settings.xml
```
* build & run
```
  > ./build.sh
  > sudo ./up.sh -d
```

## API endpoints
| Description | Example |
| --- | --- |
| XML based API description | curl http://\<host\>:\<port\>/application.wadl |
| Health check | curl http://\<host\>:\<port\>/healthcheck |
| Get/Find contacts | curl http://\<host\>:\<port\>/api/v1/contacts<br/>curl http://\<host\>:\<port\>/api/v1/contacts?firstName=John&email=.\*unknown.com <br/> curl -v -X DELETE http://\<host\>:\<port\>/api/v1/contacts - **405 Method Not Allowed** |
| Get contact by Id | curl http://\<host\>:\<port\>/api/v1/contacts/1 |
| Create contact | curl -v -X POST -H "Content-Type: application/json" -d '{"email":"first_name.last_name@gmail.com","firstName":"first_name","lastName":"last_name"}' http://\<host\>:\<port\>/api/v1/contacts |
| Update contact | curl -v -X PUT -H "Content-Type: application/json" -d '{"email":"elom_musk@gmail.com","firstName":"Elon","lastName":"Musk"}' http://\<host\>:\<port\>/api/v1/contacts/2 |
| Patch contact | curl -v -X PATCH -H "Content-Type: application/json" -d '{"email":"elom.musk@gmail.com"}' http://\<host\>:\<port\>/api/v1/contacts/2 |
| Delete contact | curl -v -X DELETE http://\<host\>:\<port\>/api/v1/contacts/2 |
