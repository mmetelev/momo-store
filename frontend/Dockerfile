# Stage 1: Build Stage
FROM node:14-alpine AS build-stage
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Stage 2: Production Stage
FROM nginx:1.27.0-alpine
COPY --from=build-stage /app/dist /app/frontend/momo-store
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
