# Instructions

## Install Docker Desktop


# Getting Vite Ready
## step 1
install vite by typing 'npm create vite@latest'in the terminal. This will prompt if you want to install the latest version

## step 2
type Y indicating Yes you want to install the latest version

## step 3
type your project name

## step 4
select you variant (typescript)

## step 5
it will prompt you to run 3 commands. 'cd what you named the directory' 'npm install' and 'npm run dev'
*Run these codes separately to avoid any problems*

## step 6
it will show
➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
  ➜  press h + enter to show help

keep note of port provided

# Create The Dockerfile

create a new file and name it 'Dockerfile' this will create a Dockerfile

Your Docker file will look similar to this
```Dockerfile
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
```

it should have a FROM and node version, set up the work directory using WORKDIR and ENVPATH
change the /app in ENV PATH and change it to what you named the WORKDIR

### install app dependencies
```
COPY package.json ./
COPY package-lock.json ./
RUN npm install --silent
RUN npm install react-scripts@3.4.1 -g --silent
```

keep this same.

### add app
COPY . ./ it will copy the file from project to docker

EXPOSE enter the port you were provided 

### lastly have CMD

CMD ["npm", "run", "dev","--","--host", "0.0.0.0"]
this includes all the command lines provided for Dockerfile
0.0.0.0 is used to refer to the host and not the container itself.


# Output
go to the src folder
locate app.tsx

delete all import except for import './App.css'

delete anything in the function and create a h1 tag and type Codin 1 to display.



# Creating Image

in terminal type docker build -t react .





