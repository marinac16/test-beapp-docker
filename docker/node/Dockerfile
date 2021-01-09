FROM node:12.18.1

WORKDIR '/'

COPY ./package.json ./

RUN npm install

COPY . .
RUN ls -l
RUN npm run build

EXPOSE 8080
