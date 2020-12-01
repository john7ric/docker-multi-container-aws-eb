FROM node:alpine
WORKDIR "/app"
COPY ./package.json ./
RUN npm install
COPY . .
CMD ["npm", "run", "build"]

FROM node:alpine

WORKDIR /app
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.f/default.conf
COPY --from=0 /app/build /usr/shared/nginx/html