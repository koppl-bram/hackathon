# Hackathon - Bay Area LLAMA - ChatGPTility

# Prereqs:
- Azure CLI + kubectl (you could just use the Azure cloud shell for this)
- NodeJS
- Docker

# Part 1: LLAMA

First of all, we need to get LLAMA up and running, and test it to make sure it works.

LLAMA runs on the CPU pretty well, but I recommend a beefy VM. E.g. Standard_D32lds_v5. I also recommend a relatively modern Linux OS, e.g. Ubuntu 20.04 LTS. Make sure to add an additional disk of 256GB. Because we need to be available for the entire world, I need everyone to deploy to a specific region as specified below:

- Viral: South Central US
- Alessio: Australia East
- Dylan: East US
- Gerald: East US 2
- Bhavya: Korea Central
- Jelle: Canada Central
- Mark: Japan East
- Kevin: Southeast Asia

SSH into it and go to /mnt and install Alpaca using Dalai LLAMA 
https://github.com/cocktailpeanut/dalai#linux 

Run the Alpaca 7B model.

It might not work immediately, why? :) 

# Part 2: Connecting to it through code

Because our initial userbase will be coders, we need to allow people to programmatically access our Alpaca model. We'll use NodeJS for testing

Use the Socket.io package to connect to your Alpaca model. 

# Part 3: Get to web scale with Service Bus!

In case we hit 100 million users, we need to scale out our Alpaca service. We'll use Azure Service Bus to decouple incoming requests from executing on the service. In that case, when Alpaca is down, we still have people's requests in our queue!

Create the Service Bus (basic pricing) and create a queue (with max concurrency of 1).

- Try sending a hello world!
- Try listening to a hello world!
- Try to send a message with a prompt with NodeJS!
- Try to receive the prompt and directly send it to Alpaca!


# Part 4: Hosting on K8S

I already got you covered with a cluster. You should have access to it. 

- Dockerize the listener
- Connect to the cluster
****- Push your image to the ACR
- Create a deployment for your service (name the deployment after your favorite dish)
- Submit a message locally and inspect the logs of your pod to make sure it works! 

# Bonus

Can you use Application Insights to track which prompts are being submitted to Alpaca? How would you do it? Ok now do it. 

# Thanks!

Dear Hackathon Participants,

I am writing to express my heartfelt gratitude to each and every one of you for participating in our recent hackathon event. Your enthusiasm, creativity, and hard work truly made the event a huge success.

I was truly impressed by the innovative solutions that you came up with during the event. It was inspiring to see how you were able to collaborate and work together to solve real-world problems with cutting-edge technology. Your passion and dedication were evident throughout the event, and it was a pleasure to watch you all in action.

I also want to thank you for your positive attitudes and your willingness to help others. The hackathon was not just about building great products, but also about fostering a sense of community and collaboration. Your willingness to share your knowledge and expertise with others was truly remarkable.


Finally, I want to congratulate all of you on your achievements. Whether you were a winner or not, you should be proud of what you accomplished during the hackathon. You have shown that with determination, hard work, and a willingness to take risks, anything is possible.


Once again, thank you all for your participation in our hackathon event. We look forward to seeing you at our next event and continuing to build a strong community of innovators.

Sincerely,

ChatGPT
