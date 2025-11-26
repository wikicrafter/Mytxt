<ol>
<li>
<ol>
<li>
<p>Open Command Prompt: Press the Windows key + X and select "Command Prompt (Admin)" from the list of options. This will open a command prompt with administrative privileges.</p>
</li>
<li>
<p>Change the DNS settings: Use the following command to change the DNS server for a specific network adapter:</p>
</li>
</ol>
<div>
<div>vbnet<button>Copy code</button></div>
<div><code>netsh interface ip set dns "Adapter Name" static &lt;DNS Server IP&gt; </code></div>
</div>
<p>Replace "Adapter Name" with the name of the network adapter you want to change the DNS settings for and replace "&lt;DNS Server IP&gt;" with the IP address of the DNS server you want to use. For example, if you want to use the Google DNS server, the command would look like this:</p>
<div>
<div>vbnet<button>Copy code</button></div>
<div><code>netsh interface ip set dns "Ethernet" static 8.8.8.8 </code></div>
</div>
<p>Note: To see the list of available network adapters and their names, use the following command:</p>
<div>
<div>kotlin<button>Copy code</button></div>
<div><code>netsh interface ip show config </code></div>
</div>
<ol>
<li>Flush the DNS cache: Use the following command to flush the DNS cache:</li>
</ol>
<div>
<div>bash<button>Copy code</button></div>
<div><code>ipconfig /flushdns </code></div>
</div>
<p>This will clear any DNS cache stored on your computer and force it to use the new DNS settings.</p>
<p>After following these steps, your computer should be using the new DNS server that you specified. You can verify the new DNS settings by using the "nslookup" command or by checking the network properties of your adapter in the Windows Control Panel.</p>
</li>
</ol>
