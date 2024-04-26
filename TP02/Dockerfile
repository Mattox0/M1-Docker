FROM node:20 AS build
WORKDIR /app
COPY package*.json ./
RUN npm i
COPY . ./
RUN npm run build

FROM buildbot/buildbot-master AS development
CMD ["npm", "run", "develop"]

FROM base as production
RUN npm i --omit=dev
CMD ["npm", "run", "start"]



