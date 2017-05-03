FROM kalilinux/kali-linux-docker:latest

# update and install dependencies
websploit w3af-console arachni nikto sqlmap websploit nmap
RUN apt-get update && apt-get install -y \
    arachni \
    nikto \
    nmap \
    sqlmap \
    w3af-console \
    websploit 
