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


___

<p>To unblock the websites and reset the configuration, you can use the <code>netsh</code> command to delete the rules that you created. Here's how to do it:</p>
<ol>
<li>
<p>Open an elevated Command Prompt by right-clicking on the Command Prompt shortcut and selecting "Run as administrator".</p>
</li>
<li>
<p>To delete the rule that blocks all websites, enter the following command:</p>
<div>
<div>javascript<button>Copy code</button></div>
<div><code>netsh advfirewall firewall delete rule name="Block All Websites" </code></div>
</div>
</li>
<li>
<p>To delete a rule that allows traffic to a specific website, enter the following command:</p>
<div>
<div>javascript<button>Copy code</button></div>
<div><code>netsh advfirewall firewall delete rule name="Allow example.com" </code></div>
</div>
<p>Replace <code>example.com</code> with the name of the rule you want to delete.</p>
</li>
<li>
<p>Repeat step 3 for each rule that you want to delete.</p>
</li>
</ol>
<p>Once you have deleted all the rules that you created, the configuration will be reset and all websites will be accessible again.</p>

---

## 🚀 Keep This Project Going

Creating comprehensive guides like this takes time, research, and lots of coffee! ☕

**Here's how you can help:**

🌟 **Star this repository** - It's free and helps others find these guides  
💝 **[Support on Ko-fi](https://ko-fi.com/gigaa)** - Buy me a coffee (or energy drink!) to fuel more content  
👤 **Follow on GitHub** - Be the first to know about new guides and updates  

*Every star, every coffee, every follow makes a difference. Thank you for your support!* 🙏✨

