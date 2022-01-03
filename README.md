# Local SSL Proxy
Use this project when you need to enable https on your local web servers. 

### Steps to use:
1) Generate an SSL cert. I like to use [mkcert](https://github.com/FiloSottile/mkcert). Put the cert and key files in the `/nginx` directory.
2) Add an entry to your local hosts file for the domain you want to add https to. You can run this 1-liner, just replace `<domain-here>` with your domain first.
    ```bash
    sudo sh -c 'echo "127.0.0.1 <domain-here>.com" >> /etc/hosts'
    ```
3) Update the nginx.conf file, again replacing `<domain-here>` with the applicable domain name.
4) Start the nginx server that will act as your SSL proxy with [docker-compose](https://docs.docker.com/compose/).
    ```bash
    docker-compose up -d
    ```