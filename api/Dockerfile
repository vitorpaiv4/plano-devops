FROM node:18 AS build

WORKDIR /usr/src/app

COPY package*.json ./
RUN npm install 

COPY . .

RUN npm run build
RUN npm ci --omit=dev && npm cache clean --force
FROM node:18-alpine3.21

WORKDIR /usr/src/app

COPY --from=build /usr/src/app/dist ./dist
COPY --from=build /usr/src/app/node_modules ./node_modules
COPY --from=build /usr/src/app/package*.json ./

EXPOSE 3000

CMD ["npm", "run", "start:prod"]