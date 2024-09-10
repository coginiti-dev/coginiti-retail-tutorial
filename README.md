# Coginiti Catalog: Retail and Marketing Projects

This repository contains Coginiti Catalog exports for two distinct projects: **Retail** and **Marketing**. These
projects are designed to showcase the implementation of ELT (Extract, Load, Transform) processes and the interaction
between different data models. It is assumed to be executed against the Postgres database.

## Project Overview

### 1. Retail Project
The Retail project is an ELT implementation for an artificial retail store. It consists of several layers organized into
CoginitiScript packages:

- **landing**: Used to randomly generate (seed) source data. This package helps in simulating data for the project,
  making it easier to work with when actual source data is not available.

- **sources**: Contains block definitions for the source data. This is where the raw data is initially ingested.

- **base**: Models the data into a set of dimensions and facts using Bill Inmon's approach. Inside the base package,
  dimensions and facts are organized into logical subject areas such as "customer," "touchpoint," "location," etc. Each
  subject area is represented as a separate CoginitiScript package, ensuring a structured and modular data model. The
  base package references the source data from the "sources" package to create this foundational data model.

- **derived_attributes**: Contains the logic for calculating individual metrics, known as "Derived Attributes." In this
  demo, we calculate "RFM" (Recency, Frequency, Monetary) segmentation for our customers, which is a crucial metric in
  retail analytics.

- **mart**: Contains blocks to build a data mart modeled as a Kimball-style star schema. This layer is designed for
  efficient querying and reporting, providing a structured way to analyze business metrics.

### 2. Marketing Project
The Marketing project demonstrates how to reference one project from another. It extracts a list of customers along with
their email addresses from the "Potential churners" RFM segmentation within the Retail project. This customer list is
then used in a marketing campaign.

## Getting Started

### Importing the Projects

To import these projects into your Coginiti catalog, follow these steps:

1. Right-click in your Coginiti catalog to open the context menu.
2. Select **Import**.
3. Navigate to the location of the exported project files from this repository.
4. Import the Retail and Marketing projects.

## Usage

Once imported, you can explore the scripts, run the transformations, and see how the data flows from raw sources to
actionable business insights. The projects are designed to be modular, allowing you to expand or customize them based on
your own requirements.

The Retail project also includes an **\_instructions** asset that provides detailed guidance on how to set up the data
for this project. Please refer to this asset to properly configure the data before running the scripts.
