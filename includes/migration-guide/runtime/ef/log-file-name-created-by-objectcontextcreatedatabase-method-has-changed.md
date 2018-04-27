### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>Il nome del file di log creato dal metodo ObjectContext.CreateDatabase è stato modificato in base alle specifiche di SQL Server

|   |   |
|---|---|
|Dettagli|Quando il metodo <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=name> viene chiamato direttamente oppure tramite Code First con il provider SqlClient e un valore AttachDBFilename nella stringa di connessione, viene creato un file di log denominato nomefile_log.ldf invece di nomefile.ldf (dove nomefile è il nome del file specificato dal valore AttachDBFilename). Questa modifica migliora il debug fornendo un file di log il cui nome si basa sulle specifiche di SQL Server.|
|Suggerimento|Se il nome del file di log è importante per un'app, l'app deve essere aggiornata in modo da prevedere il formato nomefile_log.ldf standard.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|

