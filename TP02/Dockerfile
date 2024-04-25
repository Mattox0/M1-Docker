FROM node:20 as development
WORKDIR /app
COPY package*.json /app
RUN npm i
COPY . /app
RUN npm run develop

FROM node:20 as build
WORKDIR /app
COPY package*.json /app
RUN npm i
COPY . /app
RUN npm run build

FROM node:20 as production
COPY --from=build /app/index.js /app/index.js
CMD ["node", "app/index.js"]



