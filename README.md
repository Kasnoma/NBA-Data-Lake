# NBA DATA LAKE
## Project Overview

This project automates the setup of a data lake for NBA sports analytics using AWS services such as S3, Glue, and Athena. The script fetches player data from the [sportsdata.io](https://sportsdata.io) API, processes it, and uploads it to S3 for further analysis.

![image](https://github.com/user-attachments/assets/24afd4bd-27d8-45e5-be6a-8ff55f18f594)


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

**1. Sportsdata.io account**: 

Create a free tier account on [SportsData ](https://sportsdata.io/)

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

Clone the repository using `git clone https://github.com/Kasnoma/NBA-Data-Lake.git`
