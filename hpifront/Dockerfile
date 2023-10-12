### STAGE 1: Build ###
FROM node:12.7-alpine AS build
WORKDIR /usr/src/app
COPY package.json ./
RUN npm install
COPY . .
RUN npm run build

### STAGE 2: Run ###
FROM nginx:1.17.1-alpine
COPY default.conf /etc/nginx/conf.d/default.conf
COPY --from=build /usr/src/app/dist/scrum-ui /usr/share/nginx/html
EXPOSE 80


FROM nginx:alpine
COPY  /dist/hpifront /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf
# ### STAGE 1: Build ###
# FROM node:12.7-alpine AS build
# WORKDIR /usr/src/app
# COPY package.json ./
# RUN npm install
# COPY . .
# RUN npm run build

# ### STAGE 2: Run ###
# FROM nginx:1.17.1-alpine
# COPY default.conf /etc/nginx/conf.d/default.conf
# COPY --from=build /usr/src/app/dist/hpifront /usr/share/nginx/html
# EXPOSE 4200