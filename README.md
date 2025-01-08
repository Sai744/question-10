* Here in AWS for monitoring the applications in eks prometheus is used. I have configured the prometheus server.

* Here inorder to monitor the eks servers there are 2 conditions involved.

    1. node_exporter has to be installed in the nodes that prometheus targets.
    2. Prometheus server should have decribe all ec2 instances access.

* At first prometheus server will scrape itself.

![90](https://github.com/user-attachments/assets/7310e631-1db0-4897-9cd5-c4ff2ce96e12)

* Here we are using dynamic scrapping of the nodes in eks cluster, by using tags and filters

![91](https://github.com/user-attachments/assets/d61bc057-3035-411a-8eb6-2bb2c870d4e4)

* Our main goal is to focus on that servers if any problem arises.Need to raise the alerts.
  Inorder to raise the alerts. We have prometheus rule files: in that we will add some rules.
  Need to create alert-rules directory and write some rules in yaml format.

* After creating rules in prometheus server in alerts section we can see the alerts .

![92](https://github.com/user-attachments/assets/4cac5e0f-00b7-448c-919b-b15ad350be7f)

* We will have alert manager to manage the alerts .what to do with that alert alert manager decides.
  Alertmanager opens 9093.9094 
  Now it will be in firing state that means it send alert to the alert manager.

![93](https://github.com/user-attachments/assets/fc986190-ddb0-45e5-b9e9-2640a6189a35)

![94](https://github.com/user-attachments/assets/afb63734-e210-494a-b04d-3b6ad5175e7e)

* Now written rules for CPU and Memory utilisation and raising alerts if crossed.

![95](https://github.com/user-attachments/assets/5a28bcf7-5cb3-402f-a9a8-afaf17a13d95)

![96](https://github.com/user-attachments/assets/afefa5fe-c2f1-4ae2-959d-8dac98f4450b)

* It is showing status as Firing in prometheus server. We can now observe in alertmanager.

![97](https://github.com/user-attachments/assets/40c425b6-e252-4cec-9ced-84154bd570da)

![99](https://github.com/user-attachments/assets/92d420bb-38a1-4545-ac0c-9b894c07a575)

![100](https://github.com/user-attachments/assets/b6f637bc-b4be-4eee-a55d-1c3f7dc263b4)