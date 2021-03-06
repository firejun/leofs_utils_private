
LeoFS Configuration File Converter
==================================

Overview
--------

"LeoFS Configuration File Converter" is able to convert configuration files of the previous version to the format of LeoFS v0.16.8.
It will be helpful to your operation.

Usage
--------

* Repository:
    * https://github.com/leo-project/leofs_utils/tree/master/converter
* Usage:

```
$ ./leofs_conf_converter -h
Usage: leofs_conf_converter [-h] [-a <app_config>] [-e <vm_args>]
                            [-d <dest>] [-v]

  -h, --help        Show the program options
  -a, --app_config  Individual 'app config'
  -e, --vm_args     Individual 'vm.args'
  -d, --dest_file   The file name to write
  -v, --version     Show version information

$ ./leofs_conf_converter -a test/leo_gateway.config -e test/vm.args -d leo_gateway.conf
```

* Result:

```
## LeoFS Configuration
##
## Converted the configuration
##     from "test/leo_gateway.config" and "test/vm.args"
##     to "leo_gateway.conf"
##
## ------------------------
## For Applications
## ------------------------
sasl.sasl_error_log = ./log/sasl/sasl-error.log
sasl.errlog_type = error
sasl.error_logger_mf_dir = ./log/sasl
sasl.error_logger_mf_maxbytes = 10485760
sasl.error_logger_mf_maxfiles = 5
http.handler = s3
http.port = 8080
http.num_of_acceptors = 128
http.max_keepalive = 4096
http.layer_of_dirs = 12
http.ssl_port = 8443
bucket_prop_sync_interval = 300
large_object.max_chunked_objs  = 1000
large_object.max_len_of_obj = 524288000
large_object.chunked_obj_len = 5242880
large_object.threshold_of_chunk_len = 5767168
large_object.reading_chunked_obj_len = 5242880
cache.http_cache = false
cache.cache_workers = 16
cache.cache_ram_capacity = 1073741824
cache.cache_disc_capacity = 524288000
cache.cache_disc_threshold_len = 1048576
cache.cache_disc_dir_data = ./cache/data
cache.cache_disc_dir_journal = ./cache/journal
cache.cache_expire = 300
cache.cache_max_content_len = 1048576
cache.cachable_content_type = []
cache.cachable_path_pattern = []
timeout.level_1 = 5000
timeout.level_2 = 7000
timeout.level_3 = 10000
timeout.level_4 = 20000
timeout.level_5 = 30000
managers = ['manager_0@127.0.0.1','manager_1@127.0.0.1']
log.log_level = 1
log.is_enable_access_log = true
log.is_enable_esearch = false
log.esearch.host = 127.0.0.1
log.esearch.port = 9200
log.esearch.timeout = 10000
log.esearch.esearch_bulk_duration = 3000
log.app = ./log/app
log.erlang = ./log
queue_dir = /home/yosuke/dev/test/temp/leofs-work-dir/gateway_0/work/queue
snmp_agent = ./snmp/snmpa_gateway_0/LEO-GATEWAY
log.member_dir = ./log/ring
log.ring_dir = ./log/ring

## ------------------------
## For Erlang-VM
## ------------------------
nodename = manager_0@127.0.0.1
distributed_cookie = 401321b4
erlang.kernel_poll = true
erlang.asyc_threads = 32
snmp_conf = ./snmp/snmpa_manager_0/leo_manager_snmp
```
