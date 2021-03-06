# Metatron Docker Image (Fully Engineered)

teamsprint/metatron:3.4.0

# Based on (in a row)

teamsprint/centos:7<br/>
teamsprint/jdk:8<br/>
teamsprint/hadoop:2.7.3<br/>
teamsprint/mysql:5.7<br/>
teamsprint/hive:2.3<br/>
teamsprint/druid:0.9.1<br/>

# Build the image

run build.sh

# Start a container

run run.sh

The container name is "metatron". If you don't want, just edit the scripts.

# Attach a container

run attach.sh

# Destroy containers

run destroy.sh

# IMPORTANT: After attach you might to want to to:
./start-hadoop.sh (HDFS & Yarn)<br/>
./test-hadoop.sh (Optional)<br/>

./init-mysql.sh (MySQL setting)<br/>
./start-mysql.sh (Optional; already started by init-mysql.sh)<br/>
./conn-mysql.sh (Optional)<br/>
./stop-mysql.sh (Optional)<br/>

./init-hive-metastore.sh (Mandatory)<br/>
./start-hive.sh (Optional)<br/>
./conn-hive.sh (Optional)<br/>
./stop-hive.sh (Optional)<br/>

cd $DRUID_HOME<br/>
./start-single.sh (Optional)<br/>
./stop-single.sh (Optional)<br/>

cd $METATRON_HOME<br/>
./init-metatron.sh<br/>
./start-metatron.sh (Optional; already started by init-metatron.sh)<br/>
./stop-metatron.sh (Optional)<br/>

# WARNING: DOCKER DEFAULT MEMORY SHOULD BE >= 4G

# Test
# When you run by run.sh, Metatron Discovery is at localhost:18180
# You can see other ports in run.sh

