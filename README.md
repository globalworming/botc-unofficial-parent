# set up dev

clone modules


```` bash
git clone git@github.com:globalworming/botc-unofficial-frontend.git
git clone git@github.com:globalworming/botc-e2e.git
git clone git@github.com:globalworming/botc-unofficial-backend.git
````

## start frontend

```` bash
  cd botc-unofficia-frontend
  yarn install && yarn start
````

## start backend

```` bash
  cd botc-unofficial-backend
  mvn spring-bot:run
````


## run e2e
```` bash
  cd botc-e2e
  mvn verify
````

# set up prod
``` bash
docker pull globalworming/botc-unofficial-frontend
```
or
``` bash
docker build -t globalworming/botc-unofficial-frontend .
```
then run
```` bash
docker run \
-p ${exposePort}:80 \
--env API=http://${backendHost}/api \
--env WEBSOCKET=ws://${backendHost}/ws \
globalworming/botc-unofficial-frontend:latest 
````

