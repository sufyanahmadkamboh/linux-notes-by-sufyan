# Soft vs Hard Links


bash
Copy code
ln -s /var/www/site current   # symbolic link
ln /var/www/site/file f2      # hard link (same inode)
ls -li
