FROM node:21-alpine3.18

# set working directory
WORKDIR /fortunato_franz_site

# add `/app/node_modules/.bin` to $PATH
ENV PATH /fortunato_franz_site/node_modules/.bin:$PATH

# install app dependencies
COPY package.json ./
COPY package-lock.json ./
RUN npm install --silent
RUN npm install react-scripts@3.4.1 -g --silent

# add app
COPY . ./

EXPOSE 5173

# start app
CMD ["npm", "run", "dev","--","--host", "0.0.0.0"]