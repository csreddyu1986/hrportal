# Use a suitable Node.js base image
FROM node:14

# Set the working directory
WORKDIR /app


COPY . .

# Install dependencies, including nodemon
RUN rm -rf node_modules package-lock.json
RUN npm install -g nodemon
RUN npm install express --save
RUN npm install -g node-pre-gyp
RUN npm install 
RUN npm rebuild bcrypt --update-binary





# Expose the necessary port
EXPOSE 8000

# Start the application using nodemon
CMD ["npx", "nodemon", "server.js"]
