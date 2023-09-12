# Use a suitable Node.js base image
FROM node:14

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json to the container
COPY package*.json ./

# Install dependencies, including nodemon
RUN npm install -g nodemon
RUN npm install express --save
RUN npm install -g node-pre-gyp
RUN npm install 
RUN npm update
RUN npm rebuild bcrypt --update-binary
RUN npm update


# Copy the rest of the application code to the container
COPY . .

# Expose the necessary port
EXPOSE 8000

# Start the application using nodemon
CMD ["npx", "nodemon", "server.js"]
