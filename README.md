kafka-InfluxDB
==============

A Kafka consumer for InfluxDB.
All messages sent to Kafka on a certain topic will be relayed to influxdb. 
Supports influxdb version >= 0.9 (set the respective flag)

## Example Usage

    python kafka_influxdb.py --influxdb_host 127.0.0.1 --influxdb_port 8086

or 

    python kafka_influxdb.py --configfile my_config.yaml

## Options

    kafka_influxdb.py [-h] [--kafka_host KAFKA_HOST]
                           [--kafka_port KAFKA_PORT] 
                           [--kafka_topic KAFKA_TOPIC]
                           [--kafka_group KAFKA_GROUP]
                           [--influxdb_host INFLUXDB_HOST]
                           [--influxdb_port INFLUXDB_PORT]
                           [--influxdb_user INFLUXDB_USER]
                           [--influxdb_password INFLUXDB_PASSWORD]
                           [--influxdb_dbname INFLUXDB_DBNAME]
                           [--influxdb_data_name INFLUXDB_DATA_NAME]
                           [--influxdb_columns INFLUXDB_COLUMNS]
                           [--influxdb_version DB_VERSION]
                           [--influxdb_retention_policy RETENTION_POLICY]
                           [--buffer_size BUFFER_SIZE]
                           [--verbose BOOLEAN]
                           [--statistics BOOLEAN]
                           [--configfile CONFIG_FILE]

Command line settings have precedence over config file provided settings. We provided a sample config.yaml for your convenience.

## DEPENDENCIES

See requirements.txt
Please note also that you must install the version of the influxdb python client matching your influxdb version (for 0.9 see https://github.com/influxdb/influxdb-python/tree/0.9.0_support )


## TODOs
* flush buffer if not full but some period has elapsed (safety net for low frequency input)
* offset management, if not already supported in kafka client
* create error log
