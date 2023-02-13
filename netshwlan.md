<ol>
<li>
<p><code>netsh wlan</code> is a command-line tool in Windows that can be used to manage the wireless local area network (WLAN) settings on a computer. It provides a variety of options for configuring, monitoring, and troubleshooting Wi-Fi connections.</p>
<p>With <code>netsh wlan</code>, you can perform tasks such as:</p>
<ul>
<li>Show a list of all saved Wi-Fi network login credentials on the computer</li>
<li>Delete specific Wi-Fi network login credentials</li>
<li>Set or change Wi-Fi network connection properties, such as the network security type, encryption method, and login credentials</li>
<li>Connect to a Wi-Fi network</li>
<li>Show the status of the current Wi-Fi connection</li>
<li>Troubleshoot Wi-Fi connection problems</li>
</ul>
<p>You can run <code>netsh wlan</code> commands from the Command Prompt or a script. This can be useful for automating Wi-Fi network management tasks, such as adding new Wi-Fi networks, changing security settings, or disconnecting from a network.</p>
</li>
</ol>
netsh wlan show profile

This will show you a list of all the saved Wi-Fi networks on your computer, along with their properties and configuration details.
## netsh wlan delete profile name="NetworkName"                                                                                                                                                                                               Note: The network names are case-sensitive, so make sure to use the correct capitalization when typing the network name.
## netsh wlan show interfaces - Show the status of the current Wi-Fi connection on a Window
Troubleshoot Wi-Fi connection problems: 
 Renew the IP address: If you are having trouble accessing the internet or other network resources, you may need to renew your IP address. You can do this using the following command:

 ## netsh interface ip reset "Wi-Fi"
 
 ## Show Wi-Fi pwd
 * netsh wla show profile WiFiName key=clear

