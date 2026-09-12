FROM node:20 AS builder
WORKDIR /app
COPY package.json ./
COPY index.html ./
RUN npm install
RUN npm run build

FROM nginx:alpine
COPY --from=builder /app/dist /usr/share/nginx/html