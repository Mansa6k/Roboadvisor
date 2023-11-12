# Robo-Advisor for Retirement Planning

## Overview
In this project, I built a robo-advisor using AWS services, including Amazon Lex and AWS Lambda, to recommend an investment portfolio for a retirement plan. The robo-advisor engages in a conversation with the user to gather their investment requirements and suggests a suitable portfolio based on the user's input.

## Technologies
The following technologies and services are used in this project:
- Python
- AWS Lambda
- Amazon Lex

## Features
- Configure an Amazon Lex bot with a single intent for a conversation about retirement planning.
- Build and test the robo-advisor to ensure accurate responses during the conversation.
- Enhance the robo-advisor with an AWS Lambda function to validate user input and return the investment portfolio recommendation.

## Setup and Configuration
Step 1: Configure the Initial Robo Advisor
In this section, you create the robo advisor bot and add an intent with its corresponding slots. To do so, complete the following steps:
1. Sign in to your AWS Management Console, and then create a new custom Amazon Lex botLinks to an external site. . Use the following criteria:
    * Bot name: RoboAdvisor
    * Language: English (US)
    * Output voice: Salli
    * Session timeout: 5 minutes
    * Sentiment analysis: No
    * COPPA: No
    * Advanced options: No
    * All other options: The default value
2. Add a new intent, and name it recommendPortfolio.
3. Configure sample utterances as follows (you can add more utterances if you want):
    * I want to save money for my retirement
    * I'm {age} and I would like to invest for my retirement
    * I'm {age} and I want to invest for my retirement
    * I want the best option to invest for my retirement
    * I'm worried about my retirement
    * I want to invest for my retirement
    * I would like to invest for my retirement
4. Create four slots, as the following image specifies:

<img width="817" alt="Screenshot 2023-04-13 at 10 44 05 AM" src="https://user-images.githubusercontent.com/118853744/231811049-afe6056f-43e3-4456-b824-aa9f03d2b678.png">


Remember to mark all the slots as required, as the following image shows:
<img width="1065" alt="Screenshot 2023-04-13 at 10 45 14 AM" src="https://user-images.githubusercontent.com/118853744/231811150-83066872-c00c-438d-ba28-c92b92d53c40.png">


5. Move to the “Confirmation prompt” section, and then set the following messages:
    * Confirm: Thanks, now I will look for the best investment portfolio for you.
    * Cancel: I will be pleased to assist you in the future.


Step 2: Build and Test the Robo Advisor
In this section, you build and test your robo advisor. To do so, complete the following steps:
1. To build your bot, click the Build button (in the upper-right corner of the page).
2. When the build finishes, test it in the “Test bot” pane.

Step 3: Enhance the Robo Advisor with an Amazon Lambda Function
In this section, you create an Amazon Lambda function to validate the data that a user supplies during a conversation with the robo advisor. To do so, complete the following steps:
1. Create a new Lambda function from scratch, and name it recommendPortfolio. Choose Python 3.7 as the runtime programming language.
2. In the online code editor, delete the AWS-generated default lines of code, and then paste in the provided starter code from lambda_function.py.
3. Complete the recommend_portfolio function by adding the following validation rules:
    * The value of age should be greater than zero and less than 65.
    * The value of investment_amount should be greater than or equal to 5000.
4. Complete the starter code so that once the intent is fulfilled, the bot responds with an investment recommendation based on the selected risk level, as follows:
    * None: “100% bonds (AGG), 0% equities (SPY)”
    * Low: “60% bonds (AGG), 40% equities (SPY)”
    * Medium: “40% bonds (AGG), 60% equities (SPY)”
    * High: “20% bonds (AGG), 80% equities (SPY)”

5. When you finish coding your Lambda function, test it by using the provided test events.
6. After successfully testing your code, open the Amazon Lex console, and then navigate to the recommendPortfolio bot configuration. Integrate your new Lambda function into the bot by selecting it in the “Lambda initialization and validation” and “Fulfillment” sections.
7. Build your bot, and then test it with both valid and invalid data for the slots.

### Prerequisites
- An AWS account with access to Amazon Lex and AWS Lambda
- Python 3.x

### Deployment
1. Configure the Amazon Lex bot as described in the "Configure the initial robo advisor" section.
2. Build and test the robo-advisor following the instructions in the "Build and test the robo advisor" section.
3. Create and configure the AWS Lambda function as described in the "Enhance the robo advisor with an Amazon Lambda function" section.

## Usage

To use the robo-advisor, follow these steps:

1. Ensure that the Amazon Lex bot and AWS Lambda function are set up and configured correctly, as described in the "Setup and Configuration" section.

2. Access the Amazon Lex bot using the AWS Management Console

3. Start a conversation with the robo-advisor by providing an initial message. For example, you could type "I need help with my retirement plan" or "I would like to invest for my retirement."

The robo-advisor will engage in a conversation with you to gather your investment requirements. Here's an example of a typical conversational flow:

- User: I would like to invest for my retirement
- Robo-Advisor: Thank you for trusting me to help, could you please give me your name?
- User: Andre.
- Robo-Advisor:How old are you?
- User: 23.
- Robo-Advisor: How much do you want to invest?
- User: $6500.
- Robo-Advisor: What level of investment risk would you like to take? (None,Low,Medium,High)
- User:Medium
- Robo-Advisor: Thanks, now I will look for the best investment portfolio for you



## License
This project is licensed under the MIT license 
## Contributors
Andre Johnson
