# Boston Scientific (BSX) Shares Outstanding Viewer

This project provides a single-page application to visualize the Common Stock Shares Outstanding data for Boston Scientific (BSX) and other SEC-listed companies, fetched directly from the SEC's XBRL API.

## Features

- Displays the entity name, maximum, and minimum shares outstanding values along with their respective fiscal years.
- Dynamically updates content based on the CIK (Central Index Key) provided in the URL.
- Responsive design using Tailwind CSS.

## Usage

To view the Boston Scientific (BSX) data, simply open `index.html` in your web browser.

For other companies, append a `?CIK=` query parameter to the URL with the desired company's CIK.

**Example:**
`index.html?CIK=0001018724` (for Apple Inc.)

## Data Source

Data is fetched from the U.S. Securities and Exchange Commission (SEC) XBRL API:
`https://data.sec.gov/api/xbrl/companyconcept/CIK[CIK_NUMBER]/dei/EntityCommonStockSharesOutstanding.json`

**Note on User-Agent:**
Per SEC guidance, requests to their API should include a descriptive User-Agent. In a client-side browser environment, the browser automatically sets the User-Agent. For server-side fetches or if a proxy is used, ensure the User-Agent header is set appropriately (e.g., `YourAppName/1.0 (your-email@example.com)`).

**Note on CORS and Proxies:**
Direct client-side `fetch` requests to `data.sec.gov` may be subject to Cross-Origin Resource Sharing (CORS) restrictions by browsers. This application uses a public CORS proxy (`https://api.allorigins.win/raw?url=`) for demonstration purposes to bypass these restrictions. For production environments, it is recommended to implement a robust server-side proxy or configure a specific CORS solution.

## Development

The project is a single-file HTML application (`index.html`) using inline JavaScript and Tailwind CSS via CDN.

### Files
- `index.html`: The main application file containing HTML, CSS (Tailwind CDN), and JavaScript.
- `README.md`: This file.
- `LICENSE`: The MIT License.
- `uid.txt`: An additional file provided alongside this project (its content is not directly used by `index.html` but is part of the project assets).

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.