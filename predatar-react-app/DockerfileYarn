FROM node:13.12.0-alpine

#RUN mkdir -p /home/node/app && chown -R node:node /home/node/app

# set working directory
WORKDIR /app
#WORKDIR /home/node/app

# add `/app/node_modules/.bin` to $PATH
ENV PATH /app/node_modules/.bin:$PATH
#ENV PATH /home/node/app/node_modules/.bin:$PATH

# install app dependencies
COPY predatar-react-app/package.json ./
COPY predatar-react-app/yarn.lock ./
#USER node
RUN npm install --silent
RUN mkdir node_modules/.cache && chmod -R 777 node_modules/.cache
#RUN npm install react-scripts@3.4.1 -g --silent
#RUN npm config set unsafe-perm true
RUN npm install react-scripts -g --silent


# add app
COPY /predatar-react-app/. ./

# start app
CMD ["npm", "start"]
