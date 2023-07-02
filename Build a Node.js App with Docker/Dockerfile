FROM node:6-alpine  

# The app is design to run on port 3000
EXPOSE 3000  

# Need to use package manager alpine to install tini
RUN apk add --update tini  

RUN mkdir -p /usr/src/app # make a directory and sub-directory.

# current directory in the image
WORKDIR /usr/src/app 
COPY package.json package.json 

RUN npm install && npm cache clean 

COPY . . 

# it starts container with command ‘tini – node ./bin/www’
CMD ["tini", "--", "node", "./bin/www"] 