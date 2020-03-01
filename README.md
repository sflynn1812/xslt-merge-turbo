#&nbsp;xslt-diff-turbo
---------------------------
BETA VERSION IN MASTER
---------------------------
Faster&nbsp;implementation&nbsp;of&nbsp;Tree&nbsp;Comparison&nbsp;Algorithm&nbsp;using&nbsp;XSLT&nbsp;1.0<br/>
A&nbsp;practical&nbsp;example&nbsp;is&nbsp;below.&nbsp;For&nbsp;instance&nbsp;if&nbsp;file&nbsp;a.xml&nbsp;is&nbsp;compared&nbsp;against&nbsp;file&nbsp;b.xml:<br/>
a.xml<br/>
-------------------------------<br/>
&lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"&nbsp;?&gt;<br/>
&lt;a&gt;<br/>
&nbsp;&nbsp;&lt;b&gt;test&nbsp;c&lt;/b&gt;<br/>
&nbsp;&nbsp;&lt;c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;d&gt;test&lt;/d&gt;<br/>
&nbsp;&nbsp;&lt;/c&gt;<br/>
&nbsp;&nbsp;&lt;b&gt;test&lt;/b&gt;<br/>
&nbsp;&nbsp;&lt;c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;d&gt;test&lt;/d&gt;<br/>
&nbsp;&nbsp;&lt;/c&gt;<br/>
&nbsp;&nbsp;&lt;b&gt;test&lt;/b&gt;<br/>
&nbsp;&nbsp;&lt;c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;d&gt;test&lt;/d&gt;<br/>
&nbsp;&nbsp;&lt;/c&gt;<br/>
&lt;/a&gt;<br/>
<br/>
b.xml<br/>
-------------------------------<br/>
&lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"&nbsp;?&gt;<br/>
&lt;a&gt;<br/>
&nbsp;&nbsp;&lt;b&gt;test&nbsp;2&lt;/b&gt;<br/>
&nbsp;&nbsp;&lt;c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;d&gt;test&lt;/d&gt;<br/>
&nbsp;&nbsp;&lt;/c&gt;<br/>
&nbsp;&nbsp;&lt;b&gt;test&lt;/b&gt;<br/>
&nbsp;&nbsp;&lt;c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;d&gt;test&lt;/d&gt;<br/>
&nbsp;&nbsp;&lt;/c&gt;<br/>
&nbsp;&nbsp;&lt;b&gt;test&lt;/b&gt;<br/>
&nbsp;&nbsp;&lt;c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;d&gt;test&lt;/d&gt;<br/>
&nbsp;&nbsp;&lt;/c&gt;<br/>
&lt;/a&gt;<br/>

The&nbsp;output&nbsp;would&nbsp;be&nbsp;as&nbsp;shown&nbsp;below,&nbsp;with&nbsp;the&nbsp;mismatches&nbsp;in&nbsp;a.xml&nbsp;not&nbsp;list&nbsp;in&nbsp;b.xml&nbsp;within&nbsp;tree-&gt;mismatch.&nbsp;&nbsp;The&nbsp;mismatches&nbsp;between&nbsp;b.xml&nbsp;not<br/>
not&nbsp;in&nbsp;a.xml&nbsp;under&nbsp;compare-&gt;mismatch:<br/>
&lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt;<br/>
&lt;root&gt;<br/>
&nbsp;&nbsp;&lt;root&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;tree&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;mismatch&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;b&gt;test&nbsp;2&lt;/b&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/a&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/mismatch&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;match&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;d&gt;test&lt;/d&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;b&gt;test&lt;/b&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;d&gt;test&lt;/d&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;b&gt;test&lt;/b&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;d&gt;test&lt;/d&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/a&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/match&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;/tree&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;compare&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;mismatch&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;b&gt;test&nbsp;c&lt;/b&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/a&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/mismatch&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;match&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;d&gt;test&lt;/d&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;b&gt;test&lt;/b&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;d&gt;test&lt;/d&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;b&gt;test&lt;/b&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;d&gt;test&lt;/d&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/c&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/a&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/match&gt;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;/compare&gt;<br/>
&nbsp;&nbsp;&lt;/root&gt;<br/>
&lt;/root&gt;<br/>
<br/>
This&nbsp;is&nbsp;a&nbsp;unordered&nbsp;xml&nbsp;comparison,&nbsp;though&nbsp;it&nbsp;is&nbsp;similar&nbsp;to&nbsp;many&nbsp;diff&nbsp;algorithms,&nbsp;this&nbsp;algorithm&nbsp;does&nbsp;not&nbsp;count&nbsp;order&nbsp;differences&nbsp;between<br/>
sibling&nbsp;matches&nbsp;as&nbsp;a&nbsp;difference.&nbsp;For&nbsp;instance:<br/>
a.xml<br/>
&lt;a&gt;<br/>
&nbsp;&lt;c/&gt;<br/>
&nbsp;&lt;d/&gt;<br/>
&lt;/a&gt;<br/>
<br/>
b.xml<br/>
&lt;a&gt;<br/>
&nbsp;&nbsp;&lt;d/&gt;<br/>
&nbsp;&nbsp;&lt;c/&gt;<br/>
&lt;/a&gt;<br/>
<br/>
The&nbsp;results&nbsp;of&nbsp;comparing&nbsp;these&nbsp;would&nbsp;show&nbsp;no&nbsp;differences&nbsp;therefore&nbsp;it&nbsp;is&nbsp;an&nbsp;unordered&nbsp;algorithm<br/>
<br/>
For&nbsp;larger&nbsp;examples&nbsp;it&nbsp;was&nbsp;benchmarked&nbsp;with&nbsp;10000&nbsp;node&nbsp;tree&nbsp;(xml&nbsp;file)&nbsp;compared&nbsp;to&nbsp;another&nbsp;10000&nbsp;node&nbsp;tree&nbsp;with&nbsp;2&nbsp;known&nbsp;differences&nbsp;the&nbsp;correct&nbsp;output&nbsp;was<br/>
discovered&nbsp;in&nbsp;12&nbsp;seconds.<br/>
<br/>
Generally&nbsp;speaking&nbsp;this&nbsp;algorithm&nbsp;as&nbsp;with&nbsp;any&nbsp;tree&nbsp;comparison&nbsp;algorithm&nbsp;performance&nbsp;becomes&nbsp;increasingly&nbsp;though&nbsp;slower.<br/>
Beyond&nbsp;a&nbsp;million&nbsp;nodes&nbsp;versus&nbsp;a&nbsp;similar&nbsp;million&nbsp;nodes&nbsp;xml&nbsp;file,&nbsp;the&nbsp;performance&nbsp;may&nbsp;be&nbsp;impractically&nbsp;slow.<br/>
