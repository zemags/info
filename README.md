## Clean architecture
* Easy system testing and scaling
* Easy to change dependencies (like db, frameworks)
* Any user interface
* business logic layer do not depend on database<br>

========================<br>
http requests -> handler -> service(business logic layer) -> repository(db)

JWT Token - any requests from users with token to identify user

Authentication - access to resources (401 unauthorized)

Authorization - privileges to resources (403 forbidden)

## Session
1. user
2. db
3. server create session (generate cookie, in cookie session id)
4. back to user
5. in every reqeust to server user send this cookie with session id
6. server validate and give access to resources
7. when user leave server, the server remove session and clean the cookie

## http cookie
Cookie usually stores in headers
Server set cookie with Set Cookie method, like ```Set-Cookie: session-id=token```