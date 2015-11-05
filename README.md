# JailPopDashboard
Jail Population Dashboard

Instructions to replicate the ELK stack demo (assumes a Linux OS, either native, VM, or cloud):

* Create directories to hold config and data files

mkdir -p /opt/data/

* Maker sure you're in the data directory, then clone this repo:

cd /opt/data; git clone https://github.com/code-for-tb/JailPopDashboard.git

* Issue the following command to launch the ELK container. Adjust ports as desired

docker run -it  -v /opt/data/logstash:/etc/logstash -p 5601:5601 -p 9200:9200 -p 5000:5000  --name elk sebp/elk

* Point your browser to the Kibana interface

http://<ip>:5601

* Set the time range to the last 5 years, and enjoy your browsing.

To add additional data:

* Edit the original CSV data (use Excel/Numbers/etc): 
- Remove the name field
- Reformat all fields with dates to the following format: YYYY-MM-DD

* Add the edited files to the c4tb directory in your running Docker container. Logstash should immediately detect them and begin the ingest process.
