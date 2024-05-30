# Kari David - Data Analyst Portfolio

import hashlib
import requests

def update_gravatar_image(email, image_url):
    # Generate MD5 hash of the email address
    hash_email = hashlib.md5(email.strip().lower().encode()).hexdigest()
    # Construct Gravatar URL
    gravatar_url = f"https://www.gravatar.com/{hash_email}.json"
    # Retrieve Gravatar user data
    response = requests.get(gravatar_url)
    if response.status_code == 200:
        user_data = response.json()
        # Update the Gravatar profile image
        user_data['entry'][0]['photos'] = [{'value': image_url}]
        # Send a POST request to update the profile image
        update_response = requests.post(gravatar_url, json=user_data)
        if update_response.status_code == 200:
            print("Profile picture updated successfully!")
        else:
            print("Failed to update profile picture.")
    else:
        print("Failed to fetch Gravatar user data.")

# Example usage
gravatar_email = "your_email@example.com"
new_profile_image_url = "URL_OF_YOUR_NEW_PROFILE_IMAGE"
update_gravatar_image(gravatar_email, new_profile_image_url)

This is the portfolio website for Kari David, a data analyst.

## Table of Contents

- [About](#about)
- [Projects](#projects)
- [Contact](#contact)
- [Setup](#setup)

## About

Kari David is a passionate data analyst with experience in analyzing large datasets and extracting valuable insights. This portfolio showcases Kari's projects and contact information.

## Projects

### Project 1: Sales Forecasting

- Description: Utilized machine learning techniques to forecast sales for a retail company, resulting in a 15% increase in accuracy.

### Project 2: Customer Segmentation

- Description: Segmented customers based on their purchase behavior using clustering algorithms, leading to targeted marketing strategies.

## Contact Me

- Email: kari4david@gmail.com
- Linkeden:https://www.linkedin.com/in/david-kari-5b6262193
  
## Setup

To view this portfolio website locally, follow these steps:

1. Clone this repository:
