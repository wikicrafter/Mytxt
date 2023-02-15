<p>On Windows, you can use the <code>netsh</code> command to block all websites except for several. Here's how to do it:</p>
<ol>
<li>
<p>First, open an elevated Command Prompt by right-clicking on the Command Prompt shortcut and selecting "Run as administrator".</p>
</li>
<li>
<p>To block all websites, enter the following command:</p>
<div>
<div>csharp<button>Copy code</button></div>
<div><code>netsh advfirewall firewall add rule name="Block All Websites" dir=out action=block </code></div>
</div>
</li>
<li>
<p>Next, create a new rule that allows traffic to the websites you want to allow. For example, to allow access to <code>example.com</code>, enter the following command:</p>
<div>
<div>sql<button>Copy code</button></div>
<div><code>netsh advfirewall firewall add rule name="Allow example.com" dir=out action=allow protocol=any remoteip=example.com </code></div>
</div>
<p>Replace <code>example.com</code> with the actual website you want to allow. If you want to allow multiple websites, you can create a separate rule for each one.</p>
</li>
<li>
<p>Repeat step 3 for each website you want to allow.</p>
</li>
</ol>
<p>Once you have created the rules to allow the websites you want, all other websites will be blocked.</p>
