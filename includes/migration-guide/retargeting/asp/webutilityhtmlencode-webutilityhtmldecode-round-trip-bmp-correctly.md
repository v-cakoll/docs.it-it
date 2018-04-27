### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a>Round trip corretto di WebUtility.HtmlEncode e WebUtility.HtmlDecode per BMP

|   |   |
|---|---|
|Dettagli|Per le applicazioni destinate a .NET Framework 4.5, i caratteri al di fuori del piano di base multilinguistico (BMP, Basic Multilingual Plane) eseguono correttamente il round trip quando vengono passati ai metodi <xref:System.Net.WebUtility.HtmlDecode(System.String)>.|
|Suggerimento|Questa modifica non dovrebbe avere alcun effetto sulle applicazioni correnti, ma per ripristinare il comportamento originale, impostare l'attributo <code>targetFramework</code> dell'elemento <code>&lt;httpRuntime&gt;</code> su una stringa diversa da &quot;4.5&quot;. È inoltre possibile impostare gli attributi <code>unicodeEncodingConformance</code> e <code>unicodeDecodingConformance</code> dell'elemento di configurazione <code>&lt;webUtility&gt;</code> per controllare questo comportamento indipendentemente dalla versione di destinazione di .NET Framework.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li></ul>|

