FROM node:18-alpine

WORKDIR /app

# Install only production dependencies
COPY package*.json ./
RUN npm install --production

# Copy source
COPY . .

EXPOSE 3002

CMD ["node", "index.js"]
