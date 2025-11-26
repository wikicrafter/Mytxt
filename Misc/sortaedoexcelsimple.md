<div>
<div>
<div>
<div>
<div>
<div>
<p>Sure! You can use Python and the <code>pandas</code> library to sort and extract data with the same country name and create a new Excel file with that sorted data. Here's some example code to get you started:</p>
<div>
<div>python<button>Copy code</button></div>
<div><code>import pandas as pd # Read in the Excel file and select the sheet with the data df = pd.read_excel('data.xlsx', sheet_name='Sheet1') # Group the data by country location grouped = df.groupby('Country Location') # Iterate over each group and write the data to a new file for name, group in grouped: # Create a new Excel writer writer = pd.ExcelWriter(name + '.xlsx', engine='xlsxwriter') # Sort the data by name and write it to a new sheet group_sorted = group.sort_values('Name') group_sorted.to_excel(writer, sheet_name='Sheet1', index=False) # Close the Excel writer writer.save() </code></div>
</div>
<p>Here's what this code does:</p>
<ol>
<li>Reads in the Excel file using the <code>read_excel</code> function from <code>pandas</code>.</li>
<li>Groups the data by country location using the <code>groupby</code> method.</li>
<li>Iterates over each group using a for loop.</li>
<li>Creates a new Excel writer using the <code>ExcelWriter</code> class from <code>pandas</code>.</li>
<li>Sorts the data by name using the <code>sort_values</code> method, and writes it to a new sheet in the Excel file using the <code>to_excel</code> method.</li>
<li>Closes the Excel writer using the <code>save</code> method.</li>
</ol>
<p>This code assumes that the data is in an Excel file called <code>data.xlsx</code> and that the sheet with the data is named "Sheet1". It also assumes that the columns in the Excel file are named "Name" and "Country Location". If your data is different, you may need to modify the code accordingly.</p>
<p>When you run this code, it will create a new Excel file for each country location in the data, with the name of the file being the name of the country location. Each file will contain the data for that country, sorted by name.</p>
</div>
</div>
</div>
</div>
</div>
</div>
<div>
<div>

<div>
<div>
___
</div>
</div>
</div>
</div>
<div>
<div>
<div>
<div>
<div>
<div>
<p>Here's an example of what the output files might look like:</p>
<p>Suppose the original Excel file (<code>data.xlsx</code>) contains the following data:</p>
<table>
<thead>
<tr>
<th>Name</th>
<th>Gmail</th>
<th>Phone Number</th>
<th>Country Location</th>
</tr>
</thead>
<tbody>
<tr>
<td>Alice</td>
<td><a href="mailto:alice@gmail.com" target="_new">alice@gmail.com</a></td>
<td>1234567890</td>
<td>USA</td>
</tr>
<tr>
<td>Bob</td>
<td><a href="mailto:bob@gmail.com" target="_new">bob@gmail.com</a></td>
<td>2345678901</td>
<td>Canada</td>
</tr>
<tr>
<td>Charlie</td>
<td><a href="mailto:charlie@gmail.com" target="_new">charlie@gmail.com</a></td>
<td>3456789012</td>
<td>USA</td>
</tr>
<tr>
<td>Dave</td>
<td><a href="mailto:dave@gmail.com" target="_new">dave@gmail.com</a></td>
<td>4567890123</td>
<td>Canada</td>
</tr>
<tr>
<td>Eve</td>
<td><a href="mailto:eve@gmail.com" target="_new">eve@gmail.com</a></td>
<td>5678901234</td>
<td>Australia</td>
</tr>
<tr>
<td>Frank</td>
<td><a href="mailto:frank@gmail.com" target="_new">frank@gmail.com</a></td>
<td>6789012345</td>
<td>USA</td>
</tr>
<tr>
<td>George</td>
<td><a href="mailto:george@gmail.com" target="_new">george@gmail.com</a></td>
<td>7890123456</td>
<td>Australia</td>
</tr>
</tbody>
</table>
<p>The Python code will create three output files: <code>USA.xlsx</code>, <code>Canada.xlsx</code>, and <code>Australia.xlsx</code>.</p>
<p>The <code>USA.xlsx</code> file will contain:</p>
<table>
<thead>
<tr>
<th>Name</th>
<th>Gmail</th>
<th>Phone Number</th>
<th>Country Location</th>
</tr>
</thead>
<tbody>
<tr>
<td>Alice</td>
<td><a href="mailto:alice@gmail.com" target="_new">alice@gmail.com</a></td>
<td>1234567890</td>
<td>USA</td>
</tr>
<tr>
<td>Charlie</td>
<td><a href="mailto:charlie@gmail.com" target="_new">charlie@gmail.com</a></td>
<td>3456789012</td>
<td>USA</td>
</tr>
<tr>
<td>Frank</td>
<td><a href="mailto:frank@gmail.com" target="_new">frank@gmail.com</a></td>
<td>6789012345</td>
<td>USA</td>
</tr>
</tbody>
</table>
<p>The <code>Canada.xlsx</code> file will contain:</p>
<table>
<thead>
<tr>
<th>Name</th>
<th>Gmail</th>
<th>Phone Number</th>
<th>Country Location</th>
</tr>
</thead>
<tbody>
<tr>
<td>Bob</td>
<td><a href="mailto:bob@gmail.com" target="_new">bob@gmail.com</a></td>
<td>2345678901</td>
<td>Canada</td>
</tr>
<tr>
<td>Dave</td>
<td><a href="mailto:dave@gmail.com" target="_new">dave@gmail.com</a></td>
<td>4567890123</td>
<td>Canada</td>
</tr>
</tbody>
</table>
<p>The <code>Australia.xlsx</code> file will contain:</p>
<table>
<thead>
<tr>
<th>Name</th>
<th>Gmail</th>
<th>Phone Number</th>
<th>Country Location</th>
</tr>
</thead>
<tbody>
<tr>
<td>Eve</td>
<td><a href="mailto:eve@gmail.com" target="_new">eve@gmail.com</a></td>
<td>5678901234</td>
<td>Australia</td>
</tr>
<tr>
<td>George</td>
<td><a href="mailto:george@gmail.com" target="_new">george@gmail.com</a></td>
<td>7890123456</td>
<td>Australia</td>
</tr>
</tbody>
</table>
<p>I hope this helps! Let me know if you have any further questions.</p>
</div>
</div>
</div>
</div>
</div>
</div>


![image](https://user-images.githubusercontent.com/22988682/219212314-1a7a9fb1-18f2-49b0-b635-5765c55722ce.png)
