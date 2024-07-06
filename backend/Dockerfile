# Use the predefined node base image for the app.
FROM python:3.11

# Creating base "app" directory where the source repo will reside in our container.
WORKDIR /app

# Install Poetry.
RUN curl -sSL https://install.python-poetry.org | python3 -

# Expose poetry command.
ENV PATH="/root/.local/bin:$PATH"

# Copy entire app to docker.
COPY . /app

# Install dependencies using Poetry.
RUN poetry install

# Expose app.
EXPOSE 8000