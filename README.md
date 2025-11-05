# JKTech

Install JMeter
Install Docker Desktop
login to docker account, and pull github code from https://github.com/grafana/quickpizza.git.
Run the following commands from the quickpizza folder
docker run --rm -it -p 3333:3333  ghcr.io/grafana/quickpizza-local:latest
docker run --rm -it -p 3333:3333 $(docker build -q .)
replace the user.properties file imn JMeter\bin folder.
It has got 4 types of tests
1. Dry run
2. Load test
3. Stress test
4. Endurance test
uncomment any one test type and keep other test types commented (IMPORTANT)
run the following command and observe the results
jmeter -n -t quickpizza.jmx -l quickpizza.jtl -e -o Reports
