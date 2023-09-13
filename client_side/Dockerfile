# Use an official Node.js runtime as the base image
FROM node:14

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY . .

# Install dependencies
RUN rm -rf node_modules package-lock.json
RUN npm install react-scripts --save
RUN npm install 

# Copy the rest of the app's files to the working directory
COPY . .

# Build the React app
RUN npm run build

# Expose the port the app runs on
EXPOSE 3000

# Start the app
CMD ["npm", "start"]
