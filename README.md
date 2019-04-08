# gym
Codeigniter free project for manage gym member 
Website : http://webrocom.net/codeigniter-free-project-gym-member-management-portal/
Demo : http://webrocom.net/demo/gym/auth

Nilanchal::::

download zip from - https://github.com/webrocom/gym
unzip & rename as 'gym' & copy to /var/www/html/

create schema 'gym' & execute db script 'gym.sql' 
change password in daabase.php
change base url in cnfig.php- http://localhost/gym/
restart apache- sudo systemctl restart httpd

access
http://localhost/gym/


Error:
Message: Only variable references should be returned by reference
Filename: core/Common.php
Line Number: 257

Solution:
Edit filename: core/Common.php, line number: 257

Before

return $_config[0] =& $config; 

After

$_config[0] =& $config;
return $_config[0]; 

============
restart apache - sudo systemctl restart httpd
http://localhost/gym/
credential- admin/admin
