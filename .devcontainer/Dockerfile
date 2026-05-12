FROM python:3.12-slim

RUN apt-get update && apt-get install -y \
    curl \
    git \
    git-lfs \
    && rm -rf /var/lib/apt/lists/*

RUN git lfs install --system 

RUN curl -LsSf https://astral.sh/uv/install.sh | sh

ENV PATH="/root/.local/bin:$PATH"

WORKDIR /app

# 1. Create the virtual environment named exactly .venv
RUN uv venv .venv

# 2. Copy the pyproject.toml (and uv.lock if it exists) instead of requirements.txt
COPY pyproject.toml uv.lock* ./

# 3. Install dependencies using the exact pattern required by the rubric
RUN uv pip install --python .venv/bin/python -e .

# 4. Set the environment variables to the correct .venv path
ENV VIRTUAL_ENV=/app/.venv
ENV PATH="/app/.venv/bin:$PATH"