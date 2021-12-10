# Setup ServiceNow Integration

This article explains about how to setup ServiceNow Integration in Watson AIOps.

The article is based on the the following.

- RedHat OpenShift 4.8 on IBM Cloud (ROKS)
- Watson AI-Ops 3.2.0


1. Goto the page `Data and tool integrations`

2. Click on  `Add Integration`

![ServiceNow](./images/image-00001.png)

3. In the `ServiceNow` card click on the `Add Integration` link

![ServiceNow](./images/image-00002.png)

4. Click on `Connect` 

![ServiceNow](./images/image-00003.png)

5. Enter the below field values

- Name 
- Description 
- ServiceNow URL
- User
- Password

6. Click on `Next` 

![ServiceNow](./images/image-00004.png)

7. Click on `Test Connection` to check the connection with humio

8. Click on `Next`

![ServiceNow](./images/image-00005.png)

9. Click on `Next`

![ServiceNow](./images/image-00006.png)

10. Enter the below field values

- Dataflow : Off 
- Mode: Historical ..
- Start Date : Last year date
- End Date  : tommorrow date

11. Click on `Done`

![ServiceNow](./images/image-00007.png)

12. ServiceNow connection created

![ServiceNow](./images/image-00008.png)




1. Goto the page `Data and tool integrations`

2. In the `ServiceNow` card click on the `Add Integration` link

<img src="images/2-image-1.png">

3. Enter the below field values

```
- Name 
- URL
    Sample value : https://dev-11111.service-now.com

- UserID
- Password

- Data flow - on
- Historical Data for initial AI Training
- Start date (2 years old)
- End date (current date)
```

4. Click on `Integrate`

<img src="images/2-image-2.png">
<img src="images/2-image-3.png">
<img src="images/2-image-4.png">
<img src="images/2-image-5.png">

5. Integration is created.

<img src="images/2-image-6.png">