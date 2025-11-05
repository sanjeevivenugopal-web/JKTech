# JKTech

Step 1:- Install JMeter  
Step 2:- Install Docker Desktop  
Step 3:- login to docker account, and pull github code from https://github.com/grafana/quickpizza.git.  
Step 4:- Run the following commands from the quickpizza folder downloaded from github:  

docker run --rm -it -p 3333:3333  ghcr.io/grafana/quickpizza-local:latest  
docker run --rm -it -p 3333:3333 $(docker build -q .)  

Launch the browser and navigate to http://localhost:3333 and see if the application is up and running   

Add JMeter/Bin to path environment variable.  

Replace the user.properties file imn JMeter\bin folder.  
The user.properties file has got 4 types of tests listed below, choose the test you want to run.  
1. Dry run  
2. Load test  
3. Stress test  
4. Endurance test  

#Test Execution  
Uncomment any one test type and keep other test types commented (IMPORTANT)  
Runn the following command and observe the results  
  jmeter -n -t quickpizza.jmx -l quickpizza.jtl -e -o Reports  
after every run run the following command  
  del quickpizza.jtl  
  rmdir /q /s Reports  


#Monitoring Results in Grafana  
Launch the browser  
navigate to http://localhost:3000  
Move to drilldown section on left pane.    
it will show the results for monitoring.  
