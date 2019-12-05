#Start the build phase of our Docker deployment
FROM node:alpine as builder

WORKDIR '/app'

COPY package.json .

RUN npm install

COPY . .

RUN npm run build

#Start the run phase of our Docker deplyment
FROM nginx

EXPOSE 80

COPY --from=builder /app/build /usr/share/nginx/html
