### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a>I dati sql_variant usano regole di confronto sql_variant invece delle regole di confronto del database

|   |   |
|---|---|
|Dettagli|I dati di <code>sql_variant</code> usano regole di confronto di <code>sql_variant</code> anziché regole di confronto di database.|
|Suggerimento|Questa modifica risolve il possibile danneggiamento dei dati se le regole di confronto del database differiscono da quelle di <code>sql_variant</code>. Le applicazioni basate su dati errati possono generare un errore.|
|Ambito|Trasparente|
|Versione|4.5|
|Tipo|Runtime|

