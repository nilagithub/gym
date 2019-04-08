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

in home page- memebrlist not working but other tabs working

Issue: in memberList - it shows Loading instead of showing member list
Solution:
Edit /var/www/html/gym/asset/ng/app.js  as below

Before:
PATH = window.location.protocol + "//" + window.location.host + "/demo/gym/";

After- WORKED
PATH="http://localhost/gym/";
if you mention like below it doesnt work, because mine is CENTOS os
PATH = window.location.protocol + "//" + window.location.host + "/gym/";
