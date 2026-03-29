# Image Scraper

A Flask-based web application that lets users search for any topic and automatically scrape and download matching images from Google Image Search. Downloaded images are saved locally and stored in MongoDB for persistence.

## Features

- Search any query and bulk-download matching images from Google
- Images saved to a local `images/` directory with query-based filenames
- Downloaded image data stored in MongoDB for later retrieval
- Clean web UI with search input and results display
- Logging to `scrapper.log` for error tracking

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core language |
| Flask | Web framework |
| BeautifulSoup4 | HTML parsing & image tag extraction |
| Requests | HTTP requests to Google and image URLs |
| PyMongo | MongoDB integration for image data storage |
| Flask-CORS | Cross-origin request support |

## Project Structure

```
image-scraper/
├── app.py                  # Main Flask application
├── requirements.txt        # Python dependencies
├── templates/
│   ├── index.html          # Search input page
│   ├── result.html         # Results display page
│   └── base.html           # Base HTML template
├── static/css/             # Stylesheet assets
├── images/                 # Downloaded images (auto-created)
└── Image Scraper.ipynb     # Notebook for exploration
```

## Getting Started

### Prerequisites

- Python 3.7+
- A MongoDB Atlas cluster (or local MongoDB instance)

### Installation

```bash
git clone https://github.com/smunir25/general-ai-image-scraper.git
cd general-ai-image-scraper
pip install -r requirements.txt
```

### Configuration

In `app.py`, replace the MongoDB connection string with your own:

```python
client = pymongo.MongoClient("mongodb+srv://<username>:<password>@<cluster>.mongodb.net/?retryWrites=true&w=majority")
```

### Run

```bash
python app.py
```

Visit `http://localhost:8000` in your browser.

## Usage

1. Enter a search query (e.g., `cats`, `mountains`, `cars`)
2. Click **Submit**
3. Images matching the query are downloaded to the `images/` folder
4. Image data is stored in MongoDB under the `image_scrap` database

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
