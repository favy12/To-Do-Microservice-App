FROM node:14-slim

# Install Python2 (or python-is-python3 if node-sass works with python3) and build tools
RUN apt-get update && apt-get install -y python2 build-essential && \
    ln -s /usr/bin/python2 /usr/bin/python && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /app
# Copy package files first to leverage Docker cache
COPY package*.json ./
RUN npm install
# Copy the rest of the source code
COPY . .
RUN npm run build
EXPOSE 8080
CMD ["npm", "start"]
