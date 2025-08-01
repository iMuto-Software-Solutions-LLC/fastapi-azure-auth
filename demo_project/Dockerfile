FROM python:3.12-slim-bullseye

# Install uv.
COPY --from=ghcr.io/astral-sh/uv:latest /uv /bin/uv

# Copy the application into the container.
COPY . /demo_project

# Install the application dependencies.
WORKDIR /demo_project
RUN uv sync --locked --no-cache

# Run the application.
CMD ["/demo_project/.venv/bin/fastapi", "run", "main.py", "--port", "8000"]
