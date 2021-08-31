# iperf3-throughput-tests

Original scripts were taken from: https://sandilands.info/sgordon/multiple-iperf-instances

### Usage:
* Scripts use the command `iperf`, so set an alias as: `alias iperf="iperf3"`
* Scripts create ports starting from `5000` (not included) onwards: 5001, 5002, etc
</br>

* **Run Servers in Parallel:** `bash iperf-parallel-servers <num_ports_to_open_starting_5001> <file_name>`
* Eg.: `bash iperf-parallel-servers 3 server-report`
</br>

* **Run Clients in Parallel:** `bash iperf-parallel-clients <ip_of_server> <num_ports_to_connect_to_starting_5001> <duration_of_test_in_sec> <file_name>`
* Eg.: `bash iperf-parallel-clients 1.1.1.1 3 10 client-report`
</br>

* **Run Clients Serially:** `bash iperf-serial-clients <ip_of_server> <port_on_server> <duration_of_each_test_in_sec> <num_iperf_tests> <avg_random_interval_between_tests>`
* Eg.: `bash iperf-serial-clients 192.168.0.104 5010 10 5 15`
</br>


* **Using UDP**:


```
Using UDP (instead of TCP)
By default, iperf uses TCP. If you want to use UDP instead, then both iperf-parallel-servers and iperf-parallel-clients take additional iperf options as optional command line inputs. Just add the exact iperf options you want to the end of the script command line input. For example, for the server to use UDP add the -u option:

$ ./iperf-parallel-servers 3 server-report-udp -u
For the client to use UDP, add the -u option and set the sending rate with the -b option:

$ ./iperf-parallel-clients 1.1.1.1 3 10 client-report-udp -u -b 10M
You can add any iperf options to the end, not just for UDP.
```
