FROM node:16 AS build 

WORKDIR /app
copy . /app

RUN npm install
RUN npm run build

COPY . .

EXPOSE 3000



FROM node:16-alpine  AS final

WORKDIR /app


COPY --from=build  /app/  .

RUN npm install --production


CMD ["npm", "start"]
