FROM node:18-alpine
WORKDIR /app

COPY package*.json ./
RUN npm ci --omit=dev || npm install --only=production

COPY . .

RUN mkdir -p /app/data

ENV NODE_ENV=production
ENV PORT=5000
ENV DB_PATH=/app/data/recipes.sqlite

EXPOSE 5000
CMD ["npm", "start"]
