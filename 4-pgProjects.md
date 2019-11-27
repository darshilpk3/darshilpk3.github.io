---
layout: page
title : " Post Graduate Projects" 
permalink: /PGProjects/
tagline: "By date"
---
<!--<div class="tagline">
<span class="page-title">Publications</span> <span class="page-tagline"><em>by Date</em></span>
</div>-->
<div class="manual-post" style="font-size: 17px">
<div>
<!--   <div class="manual manual-title">
  <strong>2017</strong>
  </div> -->

  <p>  <div class="manual-content">
  <a  href="\papers\Airbnb_DevOps.pdf"  style="font-weight: bolder;text-align: justify;text-justify: inter-word;">
      Airbnb Clone with CI/CD(Continuous Integration/Continuous Delivery) Pipeline - A DevOps Project</a><br>
      Developed an Airbnb clone with frontend in React.js and 4 microservices viz. Login microservice, Property microservice, Booking microservice, Dashboard Microservice. All the microservices were deployed on 4 different AWS VPCs addressing the Y-axis scale of AKF Scale Cube.Database used was MongoDB with sharding implemented to address the Z-axis scale of AKF Scale Cube.<br>
      <b>Frontend:</b> The frontned was deployed on Heroku which has inbuilt load-balancing. We implemented CI/CD pipeline on the deployed frontend with a trigger on Github Repository. As soon as any change is pushed on to the github master branch, the pipeline will start with building process and deploying it automatically on a successful build.<br>
      <b>Login Microservice and Booking Microservice:</b> These microservices' architechture was based on Kubernetes Cluster. We created an AWS EKS(Elastic Kubernetes Service) cluster with an auto-scaled node groups having capacity from 2-5. The nodes will have 2 pods in each of them running the docker image of the Login Service and another cluster running Booking Service.<br>
      <b>Property Microservice and Dashboard Micrservice:</b> These microservices' architechture uses AWS CodeBuild and AWS ECS(Elastic Container Service) cluster. The CodeBuild will trigger a new build as soon as any change is pushed to the github repository and in turn starting the CI Pipeline. On successful build, the codebuild will push the new docker image to the AWS Elastic Container Registry(ECR) on which the ECS cluster will be running. As soon as the new image is pushed with the "latest" tag to that image, the ECS Fargate cluster will acknowledge that change and will start provisioning the instances to run the latest image and hence completing the CI/CD Pipeline.
      <br><i>Nov 2019</i>.<br>
      <span>[<a href="https://github.com/nguyensjsu/fa19-281-tech-phantoms">code</a>]</span>
      <span>[<a href="https://github.com/nguyensjsu/fa19-281-tech-phantoms#architecture-diagram">detailed-architechture</a>]</span>
  </div>
</p>

  <p>  <div class="manual-content">
  <a  href="#"  style="font-weight: bolder;text-align: justify;text-justify: inter-word;">
      Developed an AP and CP Database System using Vector Clock Concept</a><br>
      This is a very unique project. I created a database system with two modes i.e Available-Partition Tolerant(AP) mode and Consistent-Partiton Tolerant(CP) mode. The database was developed using Java and exploiting its multithreading concept.
      The database system was dockerized and runs simultaneously on 5 docker containers called nodes. The containers behave differently based on different modes.<br>
      <b>AP Mode:</b> The system has no master and no slaves. Each and every nodes accept the write and read operations. When there is no partition, the operation done by one node is propogated to all the other nodes by broadcasting the new vector clock. In case of network partition, all the nodes accept write and read and update their own vector clock. After the network resets, the vector clocks are used to resolve the conflict. over here, the conflict resolution is done by accepting the latest change done by the highest node.<br>
      <b>CP Mode:</b> This system strives for consistency. Hence initially, there will be one master and 4 slaves. Only master can write into the database. Thus, all the write requests sent to slave nodes are proxied to the master node. Slave nodes can accept the read requests as the whole system is consistent. Now, if the master node goes down then the new master is elected using bully algorithm(preference to lower nodes) and a new master is elected.  
      <br><i>Oct 2019</i>.<br><span>[<a href="#">code</a>]</span>
  </div>
</p>

  <p>  <div class="manual-content">
  <a  href="https://github.com/darshilpk3/HackathonManagementSystem-using-Spring-Framework/blob/master/README.TXT"  style="font-weight: bolder;text-align: justify;text-justify: inter-word;">
      Hackathon Management System using Spring Framework</a><br>
      Hackathon Management System is a platform which brings organisers and hackers together. This system allows hackathon admins to create hackathons and the hackers to participate in the hackathons. It also provides invitation to a non-member and generates a revenue report at the end of each hackathon.<br>
      The system's frontend is developed using AntDesign and React.js. The backend is developed using Spring framework and its various modules. The system uses JPA as an Object-Relational-Mapping tool to interact with the MySQL database. Along with that, the system provides RESTful APIs developed using Spring MVC to help frontend interact with the backend system. It also takes advantage of Spring IOC and Spring Aspect Oriented Programming concepts to enhance the performance of the backend. 
      The system is deployed on AWS using Elastic BeanStalk which provides Java Runtime Enviornment and frontend was deploed on a load-balanced EC2 instances.<br><i>May 2019</i>.<br>
      <span>[<a href="https://github.com/darshilpk3/HackathonManagementSystem-using-Spring-Framework">code</a>]</span>
      <span>[<a href="https://drive.google.com/drive/folders/1Gk4fihrDWvUvOVeqDGHqsQCeixxT0YXh?usp=sharing">demo</a>]</span>
  </div>
</p>
<p>  <div class="manual-content">
  <a  href="\papers\StockPortfolioSuggestion.pdf"  style="font-weight: bolder;text-align: justify;text-justify: inter-word;">
      Stock Portfolio Suggestion Engine using Python Flask</a><br>
      Stock Portfolio Suggestion Engine provides suggestions to users on which stocks to buy based on various investment strategies like Ethical Investing, Growth Investing, Value Investing and many more. The frontend is developed using React.js and the backend is developed using Python. The backend provides RESTful APIs developed using Flask microframework which helps frontend's communication with backend. The system provides the stock report using graphs provided with the help of Rechart.js to show the current behavior of that stock. The stock data is acquired using IEX and Aplha Vantage.<br><i>Apr 2019</i>.<br><span>[<a href="https://github.com/darshilpk3/Stock-Portfolio-Suggestion-using-Python-Flask">code</a>]</span>
  </div>
  </p>

  <p>  <div class="manual-content">
  <a  href="#"  style="font-weight: bolder;text-align: justify;text-justify: inter-word;">
      LinkedIn Prototype using MERN Stack</a><br>
      Deployed a LinkedIn Prototype using MERN Stack on Amazon Web Services(AWS) carried as an Enterprise Distributed Systems project. It uses Kafka as message queues and for publish/subscribe architechture. Along with MongoDB, it also uses MySQL database for data which requires high security. It keeps in mind the enterprise wide use and thus the architechture with thich the application has been developed and hosted supports Availability and Partitioning. For faster responses, it also uses Redis caching of both the databases' data. 
      Also carried out testing using Mocha Test Cases and JMeter tool.<br><i>Nov 2018</i>.<br><span>[<a href="https://github.com/darshilpk3/LinkedIn-Prototype-using-MERN-Stack">code</a>]</span>
  </div>
</p>
   <p>  <div class="manual-content">
  <a  href="\papers\Statistical Analysis of Hospital Data using MPC.pdf"  style="font-weight: bolder;text-align: justify;text-justify: inter-word;">    
      Statistical Analysis of Hospital Data using MPC</a><br>
      With the increasing competition and the need to apply machine learning to data to get useful insights is also increasing. This project gives a proof of concept to use Multi Party Computation(MPC) in the real world to apply data mining algorithms on data which requires high security. <a href="https://en.wikipedia.org/wiki/Secure_multi-party_computation">Click here</a> to know more about Multi Party Computation.
      This project forecasts the expected number of patients of each hospital taking part in the computation using ARIMA Model. It has python flask's backend and React frontend to communicate with the backend. It uses mongoDB as database. <br><i>Nov 2018</i>.<br><span>[<a href="https://github.com/darshilpk3/Statistical-Analysis-of-Hospital-Data-using-MPC">code</a>]</span>
  </div>
</p>
   <p>  <div class="manual-content">
  <a  href="\papers\DarshilKapadia-Lab3-Report.pdf"  style="font-weight: bolder;text-align: justify;text-justify: inter-word;">
      HomeAway Prototype using GraphQL</a><br>
      Deployed a HomeAway Prototype using GraphQL to eliminate some of the problems like over-fetching, under-fetching etc that the RESTful API suffers from.<br><i>Sept 2018</i>.<br><span>[<a href="https://github.com/darshilpk3/HomeAway-using-GraphQL">code</a>]</span>
  </div>
</p>
   <p>  <div class="manual-content">
  <a  href="\papers\Homeaway_Report.pdf"  style="font-weight: bolder;text-align: justify;text-justify: inter-word;">
      HomeAway Prototype using MERN Stack</a><br>
      Deployed a HomeAway Prototype using MERN Stack on Amazon Web Services(AWS). It also uses Kafka as message queues and for publish/subscribe architechture and Redux for state management. It keeps in mind the enterprise wide use and thus the architechture with thich the application has been developed and hosted supports Availability and Partitioning. Used PassportJS and JWT Tokens for authentication.<br><i>Aug 2018</i>.<br><span>[<a href="https://github.com/darshilpk3/HomeAway-Prototype-using-MERN-Stack">code</a>]</span>
  </div>
</p>
	
   <p>  <div class="manual-content">
  <a  href="#"  style="font-weight: bolder;text-align: justify;text-justify: inter-word;">
      E-Commerce Prototype using Django</a><br>
      Developed a simple e-commerce featured website using Django. Uses mongoDB as a database.
      <br><i>Mar 2018</i>.
  </div>
</p>
</div>


