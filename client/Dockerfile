From node:16-alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
CMD ["npm", "run", "build"]

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/comf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html