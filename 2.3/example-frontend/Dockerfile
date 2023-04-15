FROM node:16.17.0-bullseye-slim AS base

EXPOSE 5000

WORKDIR /usr/src/app

COPY package.json package.json
COPY package-lock.json package-lock.json

RUN npm install -g serve


FROM base AS build-stage

COPY . .

RUN npm ci

RUN npm run build

CMD serve -s -l 5000 build