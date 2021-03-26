FROM node:12.2.0-alpine as build

WORKDIR /app

#copy react app  to the container
COPY ./reactApp /app/ 

#prepare the container for building react
RUN npm install --silent
RUN npm install react-script -g --silent
RUN npm run build


#prepare nginx
FROM nginx:1.16.0-alpine
COPY --from=build /app/build /usr/share/nginx/html
RUN rm /etc/nginx/conf.d/default.conf
COPY nginx/nginx.conf /etc/nginx/conf.d

#fire up nginx
EXPOSE 80
CMD ["nginx","-g","daemon off;"]
