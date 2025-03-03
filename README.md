

```markdown
# Article Pageviews Analysis and Keyword Clustering in Rust

This project implements a statistical analysis pipeline to process article pageviews data, extract and deduplicate keywords from article titles, perform clustering on keywords, and predict article pageviews. The project is a port of an original Python script and is implemented in Rust using several ecosystem crates.

## Features

- **Data Ingestion:** Reads article data from a tab–delimited text file.
- **Text Processing:** Tokenizes article titles, compresses status/URL information, and aggregates pageview data.
- **Normalization:** De–trends and normalizes pageviews for better statistical fitting.
- **Clustering:** Computes similarity between keywords based on article co–occurrence and clusters them using K–medoids (with support for hierarchical clustering if desired).
- **Prediction:** Predicts article pageviews based on aggregated keyword and category features.
- **Visualization:** Generates plots for clusters, dendrograms, and pageview trends using the [plotters](https://github.com/plotters-rs/plotters) crate.

## Crate Dependencies

The project makes use of the following crates:

- **[Polars](https://github.com/pola-rs/polars):** For DataFrame-like operations and CSV/TSV reading.
- **[ndarray](https://github.com/rust-ndarray/ndarray):** For numerical array operations.
- **[linfa](https://github.com/rust-ml/linfa):** For machine learning and clustering.
- **[plotters](https://github.com/plotters-rs/plotters):** For data visualization.
- **[csv](https://docs.rs/csv):** For CSV reading (if needed).

## Setup

1. **Install Rust:**

   If you haven’t already, install Rust by following the instructions at [rust-lang.org](https://www.rust-lang.org/tools/install).

2. **Clone the Repository:**

   ```bash
   git clone https://github.com/yourusername/pageviews-analysis.git
   cd pageviews-analysis
   ```

3. **Download Data:**

   Place your `Articles-Pageviews.txt` file in the project root (or update the file path in `main.rs` accordingly).

4. **Build the Project:**

   Build the project in release mode for best performance:

   ```bash
   cargo build --release
   ```

5. **Run the Project:**

   Run the executable:

   ```bash
   cargo run --release
   ```

## Project Structure

- **src/main.rs:**  
  Contains the main implementation of the analysis pipeline, including:
  - Data ingestion using Polars.
  - Text processing and feature extraction.
  - Clustering (using linfa_clustering) and prediction logic.
  - Plotting using plotters.

- **Cargo.toml:**  
  Lists all project dependencies.

## Customization

You can modify parameters such as:
- De–trending coefficients (e.g., `param_T1`, `param_T2`)
- Clustering parameters (e.g., number of clusters)
- Prediction weights and thresholds

These parameters are hardcoded in `main.rs` but can be externalized to configuration files or command-line arguments for more flexibility.

## License

This project is licensed under the MIT License.

## Acknowledgements

- Original Python implementation and methodology by Vincent Granville.
- Rust crates: [Polars](https://github.com/pola-rs/polars), [ndarray](https://github.com/rust-ndarray/ndarray), [linfa](https://github.com/rust-ml/linfa), and [plotters](https://github.com/plotters-rs/plotters).
```

---
