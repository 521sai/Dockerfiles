FROM python:3.9

# Install Chrome browser and WebDriver
RUN apt-get update && apt-get install -yq wget gnupg
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -
RUN echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list
RUN apt-get update && apt-get install -yq google-chrome-stable

# Install required Python packages
RUN pip install selenium pymongo

# Copy the scraper script to the container
COPY scraper.py ./scraper.py

CMD ["python", "./scraper.py"]
