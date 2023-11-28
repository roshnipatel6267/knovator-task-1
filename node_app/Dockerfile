# Stage 1: Build the application
FROM node:14 AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

# Stage 2: Create a lightweight image
FROM node:14-alpine
WORKDIR /app
COPY --from=build /app .
CMD ["npm", "start"]
