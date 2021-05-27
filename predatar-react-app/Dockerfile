FROM node:13.12.0-alpine

RUN mkdir -p /home/node/app && chown -R node:node /home/node/app

# set working directory
#WORKDIR /app
WORKDIR /home/node/app

# add `/app/node_modules/.bin` to $PATH
ENV PATH /app/node_modules/.bin:$PATH

# install app dependencies
COPY predatar-react-app/package.json ./
COPY predatar-react-app/yarn.lock ./

RUN npm install --silent
#RUN npm install react-scripts@3.4.1 -g --silent
RUN npm install react-scripts -g --silent

USER node
# add app
COPY /predatar-react-app/. ./

# start app
CMD ["npm", "start"]
