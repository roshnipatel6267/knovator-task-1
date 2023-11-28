# Stage 1: Build the application
FROM node:14 AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Stage 2: Create a lightweight image
FROM node:14-alpine
WORKDIR /app
COPY --from=build /app/build ./build
CMD ["npm", "start"]
