### <a name="xslt-style-sheet-exception-message-changed"></a>Modificato il messaggio di eccezione del foglio di stile XSLT

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5 il testo del messaggio di errore quando un file XSLT è troppo complesso è &quot;Foglio di stile troppo complesso.&quot; Nelle versioni precedenti il messaggio di errore era &quot;Errore di compilazione XSLT.&quot; Il codice di applicazione che dipende dal testo del messaggio di errore non funzionerà più. Tuttavia, i tipi di eccezione rimangono gli stessi e pertanto questa modifica non dovrebbe avere un impatto reale.|
|Suggerimento|Aggiornare il codice dell'app che dipende dal messaggio di eccezione da questa condizione di errore in modo che preveda il nuovo messaggio oppure, ancora meglio, aggiornare il codice in modo che dipenda solo dal tipo di eccezione (<xref:System.Xml.Xsl.XsltException?displayProperty=name>), che non è stato modificato.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li></ul>|

