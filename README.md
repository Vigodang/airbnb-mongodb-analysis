# Airbnb MongoDB Analytics: Sydney & Montreal

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-NoSQL%20Analytics-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook%20Workflow-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed%20Analytics%20Case%20Study-2E7D32?style=for-the-badge)

## 📖 Executive Summary (About)

This project is a MongoDB-powered analytics case study using the `sample_airbnb.listingsAndReviews` document collection to answer practical questions about Airbnb pricing, review behaviour, guest requirements, amenities, and geospatial listing discovery. The analysis is implemented in a Jupyter notebook with PyMongo and demonstrates how document databases can support analytical workloads that combine nested fields, arrays, embedded reviews, geospatial coordinates, and semi-structured listing metadata.

The business problem is marketplace intelligence: hosts, travellers, and platform analysts need fast answers to questions such as which suburbs provide strong value, which amenities dominate a market, where affordable high-review properties are located near landmarks, and which users drive review activity. Instead of flattening all data into relational tables, this project uses MongoDB's native document model and aggregation framework to query the data in its original nested structure.

The final outcome is a portfolio-grade NoSQL analytics workflow covering collection restoration, index creation, targeted find queries, privacy-preserving updates, aggregation pipelines, `$unwind` transformations, `$bucket` price segmentation, and `$geoNear` geospatial search. The notebook surfaces concrete insights such as affordable Sydney listings under $200 with 100+ reviews, Montreal houses under $100 with required amenities, high-rating low-cost Australian suburbs, Sunday as the most active review day, and Opera House-proximate listings within 5 km.

## 🚀 Technical Highlights & Business Value

- **Document database analytics:** Queries nested Airbnb documents directly across address, host, amenities, availability, reviews, property metadata, and geospatial fields.
- **Advanced MongoDB aggregation:** Uses `$match`, `$group`, `$sort`, `$project`, `$limit`, `$unwind`, `$bucket`, `$geoNear`, accumulator expressions, and array slicing to produce business-ready summaries.
- **Geospatial decision support:** Builds a `2dsphere` index and retrieves affordable, highly reviewed listings within 5 km of the Sydney Opera House, sorted by physical distance.
- **Data governance and privacy:** Updates 316 reviewer-name occurrences from `Robert` to `Anonymous` using positional array filters, validating the result with before/after counts.
- **Marketplace insights:** Identifies pricing bands, country-level average prices, top reviewer activity, high-value suburbs, dominant US house amenities, and review-day demand patterns.

## 🛠️ Tech Stack & Skills Demonstrated

* **Languages:** Python, MongoDB Query Language
* **Frameworks & Libraries:** PyMongo, dnspython, Pandas, Jupyter Notebook, BSON utilities
* **Databases & Tools:** MongoDB, MongoDB Atlas or local MongoDB, `sample_airbnb` dataset, 2dsphere geospatial indexing
* **Methodologies:** NoSQL Data Modelling, Document-Oriented Querying, Aggregation Pipeline Design, Geospatial Search, Array Unwinding, Price Bucketing, Nested-Field Filtering, Projection Design, Data Privacy Transformation
* **Domain Skills:** Short-Term Rental Analytics, Marketplace Intelligence, Tourism Data Analysis, Pricing Strategy, Review Behaviour Analysis, Amenity Benchmarking, Location-Based Search

## 🔑 Keywords & Tags

MongoDB analytics, Airbnb data analysis, NoSQL, PyMongo, aggregation pipeline, geospatial query, 2dsphere index, `$geoNear`, `$unwind`, `$bucket`, nested documents, marketplace analytics, short-term rentals, Jupyter Notebook, data engineering

## 🏗️ Architecture & Methodology

The workflow connects to a MongoDB database named `sample_airbnb` and works with the `listingsAndReviews` collection. The notebook supports restoring the collection from `listingsAndReviews.bson`, then recreates operational indexes on `_id`, `name`, `address.location`, and a compound listing-attribute index over `property_type`, `room_type`, and `beds`.

The analytical layer is organised as a sequence of business questions implemented directly in MongoDB. Simple `find` queries handle targeted listing retrieval with numeric ranges, nested-field predicates, array membership, and projection control. Update operations demonstrate document mutation patterns, including array-filtered privacy edits and amenity enrichment with `$addToSet`.

The core analytics are implemented with MongoDB aggregation pipelines. Price and cancellation-policy statistics are grouped by property type, affordable Australian suburbs are ranked by average rating and price, review activity is transformed with `$unwind` and date functions, country-level average prices are computed across reviewed properties, and high-activity reviewers are summarised with review counts plus sampled property lists.

For spatial analytics, the project creates a geospatial index and uses `$geoNear` to identify listings within a 5 km radius of the Sydney Opera House. The pipeline combines distance calculation with pricing, review-count, and accommodation-capacity filters, then returns concise results including name, price, number of reviews, capacity, distance in metres, and street address.

## 📊 Analytical Results & Insights

| Analysis Area | Key Result |
| :--- | :--- |
| Sydney affordability filter | Found multiple listings under $200, accommodating 4-5 guests, with 100+ reviews |
| Reviewer privacy update | Replaced 316 `Robert` review-name occurrences; post-update count returned 0 |
| Australian suburb ranking | Summer Hill, Padstow, Turrella, Silverwater/Newington, and Canterbury ranked as low-price suburbs with 90+ average ratings |
| Review activity | Sunday had the highest review-posting activity with 28,959 reviews, followed by Monday with 24,906 |
| Country price comparison | Portugal, Spain, and Canada were the lowest average-price countries among reviewed listings |
| Top reviewer activity | The most active reviewer name, David, appeared in 1,072 reviews |
| US house amenities | Wifi, Essentials, Kitchen, Smoke detector, TV, and Hangers ranked among the most common amenities |
| Sydney Opera House proximity | Returned 10 qualifying listings within 5 km, including options around 1.03 km to 3.28 km away |
| Price bucketing | The largest observed price bucket was $0-$99 with 2,181 listings and an average price of approximately $59.24 |

## 📂 Repository Structure

```text
airbnb-mongodb-analysis/
|-- README.md                                           # Project documentation
|-- requirements.txt                                    # Python dependencies
`-- Airbnb_Data_Analysis_MongoDB/
    `-- notebooks/
        `-- Sydney_Montreal_Airbnb_Analytics.ipynb     # Main MongoDB analysis
```

## ▶️ How to Reproduce

1. Clone the repository.

```bash
git clone https://github.com/Vigodang/airbnb-mongodb-analysis.git
cd airbnb-mongodb-analysis
```

2. Install Python dependencies.

```bash
pip install -r requirements.txt
```

3. Start MongoDB locally or provide a MongoDB Atlas connection string.

```bash
set MONGO_CONNECTION_STRING=mongodb://localhost:27017
```

4. Open the notebook and run the analysis.

```bash
jupyter notebook Airbnb_Data_Analysis_MongoDB/notebooks/Sydney_Montreal_Airbnb_Analytics.ipynb
```

The notebook expects access to the MongoDB `sample_airbnb.listingsAndReviews` collection. If restoring from BSON, place `listingsAndReviews.bson` next to the notebook and run the provided `replace_collection` helper before executing the task queries.

## 📌 Project Outcome

This repository demonstrates practical NoSQL analytics beyond simple CRUD operations. It shows how MongoDB can support real marketplace analysis through nested-document querying, array transformation, aggregation design, geospatial search, privacy-aware updates, and concise business reporting. The result is a strong portfolio example for data engineering, database analytics, and backend-oriented data science roles.
