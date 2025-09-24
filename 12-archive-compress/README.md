# Archiving & Compression


bash
Copy code
# tar
tar -cvf backup.tar /etc
tar -czvf backup.tar.gz /etc
tar -xzvf backup.tar.gz -C /restore

# zip
zip -r site.zip /var/www/site
unzip site.zip -d /tmp/site
