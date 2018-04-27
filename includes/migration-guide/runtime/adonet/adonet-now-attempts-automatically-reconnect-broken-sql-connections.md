### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a>ADO.NET ora tenta di riconnettere automaticamente le connessioni SQL interrotte

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5.1, .NET Framework tenterà di riconnettere automaticamente le connessioni SQL interrotte. Anche se ciò in genere renderà più affidabili le app, in alcuni casi limite un'app deve sapere che la connessione è stata interrotta in modo da poter adottare determinate azioni alla riconnessione.|
|Suggerimento|Se questa funzionalità non è auspicabile per motivi di compatibilità, è possibile disabilitarla impostando la proprietà <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=name> di una stringa di connessione (o <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=name>) su 0.|
|Ambito|Microsoft Edge|
|Versione|4.5.1|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)?displayProperty=nameWithType></li></ul>|

