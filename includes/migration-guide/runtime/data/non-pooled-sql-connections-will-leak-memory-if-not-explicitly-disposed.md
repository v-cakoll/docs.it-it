### <a name="non-pooled-sql-connections-will-leak-memory-if-not-explicitly-disposed"></a>Le connessioni SQL non in pool perdono memoria se non vengono eliminate in modo esplicito

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5 le connessioni SQL non in pool che non vengono esposte in modo esplicito (attraverso Dispose, Close o using) perdono memoria|
|Suggerimento|Questo problema viene risolto in un aggiornamento di manutenzione di .NET Framework 4.5. Per risolvere questo problema, aggiornare .NET Framework 4.5 o eseguire l'aggiornamento a .NET Framework 4.5.1 o versioni successive. In alternativa, il problema può essere evitato usando <xref:System.Data.SqlClient.SqlConnection?displayProperty=name> in un criterio &#39;using&#39; (la procedura consigliata) o chiamando in modo esplicito Dispose o Close quando la connessione non è più necessaria.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String%2CSystem.Data.SqlClient.SqlCredential)?displayProperty=nameWithType></li></ul>|

