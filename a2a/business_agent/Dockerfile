FROM python:3.13-slim

# Create non-root user
RUN useradd -m agent

WORKDIR /app

# Copy files
COPY --chown=agent:agent . .

# Install dependencies
RUN pip install uv && uv sync

# Switch to non-root user
USER agent

# Run
CMD ["uv", "run", "business_agent"]
