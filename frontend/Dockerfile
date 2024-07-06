# Use the predefined node base image for the app.
FROM node:18

# Creating base "app" directory where the source repo will reside in our container.
WORKDIR /app

# Copy entire app to docker.
COPY . /app

# Install node dependencies.
RUN npm install

# Expose app.
EXPOSE 5173