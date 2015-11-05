# JailPopDashboard
Jail Population Dashboard

Instructions to replicate the ELK stack demo (assumes a Linux OS, either native, VM, or cloud):

* Create directories to hold config and data files

mkdir -p /opt/data/logstash; mkdir -p /opt/data/logstash/c4tb;  mkdir -p /opt/data/logstash/conf.d; \
mkdir -p /opt/data/logstash/templates

* Edit the original CSV data (use Excel/Numbers/etc): 
- Remove the name field
- Reformat all fields with dates to the following format: YYYY-MM-DD

* Place the data files in the /opt/data/logstash/c4tb directory.

* Place the logstash.conf file in the /opt/data/logstash/conf.d directory

* Place the arrest-template.json file in the /opt/data/logstash/templates directory

* Issue the following command to launch the ELK container. Adjust ports as desired

docker run -it  -v /opt/data/logstash:/etc/logstash -p 5601:5601 -p 9200:9200 -p 5000:5000  --name elk sebp/elk

* Point your browser to the Kibana interface

http://<ip>:5601

8. Set the time range to the last 5 years, and enjoy your browsing.
