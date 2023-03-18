# Command to list commands done 

iptables -L -n -v

# Command to flush already done commands

iptables -F

# Command to remove or prevent people to connect to you TCP CONNECTION

iptables -A INPUT -p tcp --match multiport --sports 0:65535 -j REJECT --reject-with tcp-reset

iptables -A INPUT -p tcp --match multiport --sports 0:65535 -j ACCEPT 

# Command to reject some malicious ip to DDOS you TCP CONNECTION

iptables -A INPUT -p tcp -s 1.1.1.1 --match multiport --sports 0:65535 -j REJECT --reject-with tcp-reset

The use of --sports can be like '--sports 1000,1001,1003' or '--sports 0:8000' 

# Command to save it 

iptables-save 
