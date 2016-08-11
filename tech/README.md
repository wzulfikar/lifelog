# Tech
Things related to technology

# Restrict Access with Nginx

- in ur server file, use `deny all`
- if want to access from ur ip, use `allow you.ip.here`
- or use http basic auth

**Using HTTP Basic Auth**
- `auth_basic "any title here"`
- `auth_basic_user_file /etc/nginx/.htpasswd`

to create file for storing user & pass:
- issue `sudo htpasswd /etc/nginx/.htpasswd UsernameHere` n insert the pass upon prompt.
