# spotify-end-to-end-data-engineering-aws

## 🎵 Spotify Top 10 Data Engineering Pipeline

## 🚀Project Overview

This project is a fully automated ETL pipeline that tracks Spotify’s Top 10 Global songs every 24 hours. The pipeline begins by connecting to Spotify’s API to extract live playlist data. Once the data is pulled, it undergoes cleaning, normalization, and structuring to produce organized datasets for songs, albums, and artists. These processed datasets are stored in Amazon S3, allowing for seamless cloud-based analytics. The main goal of the project is to build a serverless, scalable workflow that delivers fresh, structured data every day without requiring any manual intervention.

## 🏗 ETL Pipeline Flow

Architecture diagram of the serverless Spotify Top 10 ETL pipeline

<img width="622" height="356" alt="image" src="https://github.com/user-attachments/assets/daaf5ecf-7d33-4ff3-83ac-7f30812fb26a" />

The pipeline consists of three main stages: Extraction, Transformation, and Load & Analysis.

 ## **Extraction Stage**

Spotify API: Fetches Top 10 playlist data daily

AWS Lambda: Handles extraction 

Amazon CloudWatch: Triggers the Lambda function every 24 hours

Amazon S3: Stores raw JSON files

 ## **Transformation Stage**

Processes raw JSON into structured datasets using Pandas

Created separate tables for:

Songs: ID, name, duration, popularity, album, artist

Albums: ID, name, release date, total tracks

Artists: ID, name, profile links

Ensures data is clean, deduplicated, and query-ready

Saves transformed CSV files back to S3

 ## **Load & Analysis Stage**

AWS Glue Crawler: Infers table schema automatically

AWS Glue Data Catalog: Manages metadata for easy querying

Amazon Athena: Queries datasets directly in the cloud

## **✨ Key Highlights**

Automated Daily ETL: Pipeline updates every 24 hours

Clean, Structured Data: Ready for analysis of songs, albums, and artists

Serverless & Scalable: Fully cloud-native using AWS Lambda, S3, Glue, and Athena

Metadata Management: Glue Crawler detects schema automatically, simplifying analytics

