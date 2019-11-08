# download base image
FROM node:alpine as builder

#specify directory in container
WORKDIR /app

#copy dependency file into workdir
COPY package.json .

#install dependencies into img Fs
RUN npm install

#copy all other files into workdir
COPY . .

#specify defualt command
RUN npm run build



FROM nginx
COPY --from=builder /app/build /usr/share/nginx/html
