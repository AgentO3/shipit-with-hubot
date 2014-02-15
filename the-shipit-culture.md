- What is the ShipIt culture
  - Make it easy
  - Make it accessible
  - Make it fun
  - Make it safe
- Tools & Techniques
  - The problem with commandline tools
  - Making deployment fun
- The results
  - Multiple deployments to production a day
  - Code ownership is maintained
  
  
As a startup it's important to be able to get new features and bug fixes into production. The reason this is important is because code has no value until it's in production. That performance improvement sitting on your laptop does not improve anything until it's on the production server and it's really just a guess that it improves anything until it's interacting with production workload. That new UI feature that customers are going to go crazy for, well that's just a guess until they use it and confirm your hypothesis. This why we have worked hard to establish what we call a "ShipIt" culture.

The goal of "ShipIt" is to nurture a company culture of getting code into production early and often. As an organization we have established some guidelines for our deployment process to help facilitate this. 

*Deployments should be*

- Easy
- Safe
- Accessible
- Fun

When your first starting out your deployment process will most likely be a command line tool of that you run manually, probably something like rsync or Capistrano. As your team grows you begin to find issues with command line tools. 


