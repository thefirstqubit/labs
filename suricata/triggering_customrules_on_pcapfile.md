# Triggering Custom Rule on .pcap file & Use of jq Command

<img width="838" alt="examin_custom_rule" src="https://github.com/user-attachments/assets/e26f0a3a-48ce-4906-93c9-0f3be5ab8760" />

cat custom.rules to display the content of the custom rule file.  Rule is designed to trigger an alert message, "GET on wire" for HTTP traffic.

sudo suricata '-r sample.pcap -S custom.rules -k none'  command used for running the customs rules on the sample.pcap file. 

<img width="841" alt="list_files_examin_fast logfile_after triger" src="https://github.com/user-attachments/assets/ad2c24f4-896a-4262-863b-c6dc8b76abd5" />

List the files of log/suricata and view contents of fast.log . Entries confirm that the custom rule "GET on wire" (with sid:12345 and rev:3) was triggered twice.

<img width="840" alt="3_examin eve json files" src="https://github.com/user-attachments/assets/53a75e3a-6d00-4651-8600-c61c3c6a4983" />

Examine the eve.json file by piping its content to 'cat /var/log/suricata/eve.json'

<img width="779" alt="4_jq command _improved format" src="https://github.com/user-attachments/assets/61e36266-89ab-48ff-a277-dbd125fdc7e4" />

Make the eve.json output more readable useing the jq command-line. Image now displays the first JSON event in a nicely formatted, readable manner, making it easier to inspect all the fields.

<img width="841" alt="5_jq_specific_event_data" src="https://github.com/user-attachments/assets/a5aced7a-7bdd-4ae3-8606-f35ed6ebbb67" />

Extract specific fields from the eve.json file using jq -c for more targeted analysis. Output now shows a clean, concise list of arrays, each representing one alert that was triggered. 
