sudo vi /lib/systemd/system/code-server@.service
sudo systemctl restart code-server@narayanan_kmu.service
sudo systemctl daemon-reload
sudo systemctl restart code-server@narayanan_kmu.service
sudo systemctl status code-server@narayanan_kmu.service


air-frame
gcloud compute ssh --ssh-flag "-L 4100:localhost:4100" quickbytes

code-server 
gcloud compute ssh --ssh-flag "-L 8080:localhost:8080" quickbytes