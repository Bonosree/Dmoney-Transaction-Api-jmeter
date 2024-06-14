# Project title: Jmeter Performance Testing
## Project Overview: This project is designed for creating JMX files using Apache JMeter to automate a series of positive test cases based on the following scenario.
- Admin creates an agent and a customer
- Deposit 2000 tk to agent from system account (fromAc: SYSTEM)
- Deposit 1000 tk to customer from agent account
- Check balance from customer account
- Withdraw 500 tk from customer account
- Payment 200 tk from customer account (Create any merchant acc or search any merchant for payment)
  
-The main objective is to simulate these actions and measure the performance of the system under test.

## Prerequisites:
- Java (JDK 8 or above)
- Apache JMeter (version 5.0 or above)

## Installation:
- Install Java: Ensure that JDK 8 or above is installed on the system or downloaded from the java official website
- Install Apache JMeter: Visit the Apache JMeter website and download the latest version of JMeter.Follow the installation instructions provided in the JMeter documentation for the operating system.
- Setup JMETER_HOME and path

## Running JMeter:
 - Change to the bin directory
 - Run the jmeter (Un*x) or jmeter.bat (Windows) file.

## Creating The JMX file: 
Follow the steps and create JMX file  for the given scenario:
 1. Open JMeter:
    Launch JMeter and open the .jmx files located in the project directory.
 2. Create Test Plan:
    - After opening jmeter create a new test plan
    - add Thread Group: add > threads (users) > Thread Group
    - set the no of threads and ramp-up period and loop count

3. Add HTTP Requests:
    - right click on the thread group: Add->Sampler->HTTTP Request
    - set the method as POST
    - set the PATH
4. Add HTTP requests: add an HTTP request for the admin to create an agent and customer account 
   - Create Agent and Customer Account :
      - method: POST
      - set PATH
      - Parameter: {"role": "agent'} and {"role" : "customer"}
    - Deposit to account: add an HTTP request to deposit 2000 tk to the agent from the system account
      - Method: POST
      - set PATH
      - Parameter: { "from_account": "SYSTEM", "to_account":"", "amount":2000 }

    - Check Agent balance: Add an HTTP request to check the agent balance
      - Method: Get
      - Set PATH
    - Withdraw By Customer Account: Add an HTTP request to withdraw 500 tk from the customer account
       - Method: POST
       - Set PATH
       - Parameter: { "from_account":" ", "to_account":" ", "amount":600}
       - 
   - Payment from Customer Account: Add an HTTP request to pay 1000 tk from the customer account
       - Method: POST
       - Set PATH
       - Parameter : { "from_account":" ", "to_account":" ", "amount"100}
    
   - Add listener to see the result 
   -  Run Tests: Execute the test plan to simulate user activity and collect performance data.

## Documentation : 
https://documenter.getpostman.com/view/1844288/2s9YeABaGp

## Output :
![My Image]![image](https://github.com/Bonosree/Dmoney-Transaction-Api-jmeter/assets/59661684/27b0ce8b-a9ed-4837-abc1-4f2c150c81c1) 
![My Image](![image](https://github.com/Bonosree/Dmoney-Transaction-Api-jmeter/assets/59661684/6442c1d4-bb73-4c01-9748-69147ec859a8)
)





