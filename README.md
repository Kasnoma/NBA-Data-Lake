# NBA DATALAKE
## Project Overview

This project is a serverless application that fetches sports game data from an external API and sends notifications to subscribers via Amazon Simple Notification Service (SNS). It uses AWS Lambda, Amazon EventBridge, and the SportsData.io API to deliver game updates in real time.

## Project Structure

```
nba-data-lake/
├── policies/
│   ├── iam-role.json        
├── src
│   ├── setup_nba_data_lake.py          
├── .env
├── .gitignore
├── cleanup.py
├── README.md
└── requirements.txt

```    


## Prerequisites
Before you commence this project, you must have the following:

**1. Sportdata.io account**: 

Create a free tier account on [SportData ](https://sportsdata.io/)

Follow the steps to get your NBA API Key.

**2. AWS Credentials:**

You'll need your Access Key, Secret Key, default region, and output format.

If you dont already have an AWS account you can create a free tier account using this [link](https://signin.aws.amazon.com/signup?request_type=register).

After your registration, logon and create a unique user

Create an access key for this user

Initialize your AWS Cli using this command: 

`aws configure`

**3. AWS Credentials:**

Version 3.7 or higher is required.

Confirm you have python and pip installed already by running this command:

`python3 --version`

`pip --version`

`pip install requirements.txt`

If you don't, follow the installation guide on [python official page](https://www.python.org/downloads/) 

**4. Configure environment variables (.env):**

AWS_BUCKET_NAME=your_bucket_name

SPORTS_DATA_API_KEY=your_api_key

NBA_ENDPOINT=https://api.sportsdata.io/v3/nba/scores/json/Players

AWS_REGION=your_region


5. **Run the script**
   
Navigate to the src/ and run this command:

```
python3 setup_nba_data_lake.py
```

## Project Walkthrough

**Check for  appropriate resources**
Go to your AWS management console and check if these resources have been created:

1. The S3 bucket containing the raw_data from the NBA API.
   
2. The database and table has been created in AWS Glue.

**Amazon Athena**
Navigate to Amazon Athena and run this query
```
SELECT FirstName, LastName, Position, Team
FROM nba_players
WHERE Position = 'PG';
```
