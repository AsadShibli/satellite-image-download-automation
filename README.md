# Sentinel-2 Satellite Image Downloader

This script automates the process of downloading Sentinel-2 satellite images from Google Earth Engine (GEE) for specific areas of interest (AOIs) and uploading them to Google Drive.

## Features

- **Automated Daily Downloads**: The script runs daily to check for new images and download them.
- **Custom AOIs**: Define custom areas of interest (AOIs) to monitor.
- **Image Export**: Exports images to Google Drive in the specified format.
- **Logging**: Keeps a log of activities and errors.

## Setup

### Prerequisites

- Python 3.12.2
- Google Earth Engine Python API
- Folium
- Schedule
- JSON
- OS
- Logging

### Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/sentinel2-downloader.git
    cd sentinel2-downloader
    ```

2. Install the required Python packages:

    ```bash
    pip install earthengine-api folium schedule
    ```

3. Authenticate with Google Earth Engine:

    ```python
    import ee
    ee.Authenticate()
    ee.Initialize()
    ```

### Configuration

1. Update the `authenticate_ee` function with your GEE project details.
2. Define your areas of interest (AOIs) and their corresponding centers in the `main` function:

    ```python
    aoi_coastal = ee.Geometry.Polygon(
        [[[-123.2, 37.6], [-123.2, 38.2], [-122.1, 38.2], [-122.1, 37.6], [-123.2, 37.6]]])
    aoi_port = ee.Geometry.Polygon(
        [[[-118.32, 33.68], [-118.32, 33.82], [-118.17, 33.82], [-118.17, 33.68], [-118.32, 33.68]]])
    
    center_coastal = [37.9, -122.65]
    center_port = [33.75, -118.25]
    ```

## Usage

1. Run the script:

    ```bash
    python main.py
    ```

2. The script will run daily at midnight to check for new images, process them, and upload them to Google Drive.

## Logging

Logs are saved to `satellite_image_download.log` to track the script's activities and errors.

## Contributing

Feel free to submit issues or pull requests if you want to contribute to this project.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

