<h2>Working with data</h2>

<p>A good chart begins with good data.</p>

<p>Data can be invented, generated, or found.</p>

<p>Finding the right data and handling it in a way that you can actually use it is found to be one of the hardest part of data visualisation.</p>

<p>You can invent <code>[1,2,4]</code> and you have some data.</p>

<h2>To parse data from a CSV</h2>

<ul>
	<li>Import csvParse and autoType from <a href="https://d3js.org/d3-dsv">d3-dsv</a></li>
	<li>Export a default object named csvParse with your csv, with the autotype parameter</li>
</ul>
<pre><code>import &#123; csvParse, autoType &#125; from &#x27;d3-dsv&#x27;;
export default csvParse(`A,B
2,3
1,2
4,5
9,10`, autoType)</code></pre>
