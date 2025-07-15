FROM python:3.9-slim

WORKDIR /app

RUN apt-get update && apt-get install -y \
    build-essential \
    libglib2.0-0 \
    libsm6 \
    libxrender1 \
    libxext6 \
    git && \
    pip install --upgrade pip

# Install Argo Translate core and required files
RUN pip install argostranslate==1.8.0 argostranslatefiles==1.0.6

# Clone LibreTranslate
RUN git clone https://github.com/LibreTranslate/LibreTranslate.git . && \
    pip install -e .

# Expose default port
EXPOSE 5000

# Start the app
CMD ["python3", "-m", "libretranslate"]
