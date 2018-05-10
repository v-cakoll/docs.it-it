### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a>Le analisi dello stack ottenute quando si usano file PDB portatili ora includono informazioni su file di origine e righe, se richieste

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7.2, le analisi dello stack ottenute quando si usano file PDB portatili includono informazioni su file di origine e righe, se richieste. Nelle versioni precedenti a .NET Framework 4.7.2 le informazioni su file di origine e righe non sono disponibili quando si usano file PDB portatili, anche se richieste in modo esplicito.|
|Suggerimento|Per le applicazioni destinate a .NET Framework 4.7.2 è possibile rifiutare esplicitamente le informazioni su file di origine e righe quando si usano file PDB portatili, nel caso non siano opportune, aggiungendo il codice seguente alla sezione <code>&lt;runtime&gt;</code> del file <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Per le applicazioni destinate alle versioni precedenti di .NET Framework, ma eseguite in .NET Framework 4.7.2 o versioni successive, è possibile acconsentire esplicitamente alle informazioni su file di origine e righe quando si usano file PDB portatili aggiungendo il codice seguente alla sezione <code>&lt;runtime&gt;</code> del file <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.7.2|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)?displayProperty=nameWithType></li><li>`System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)`<li><xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)?displayProperty=nameWithType></li></ul>|

