### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a>SqlBulkCopy usa la codifica della colonna di destinazione per le stringhe

|   |   |
|---|---|
|Dettagli|Nell'inserire i dati in una colonna, <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=name> usa la codifica della colonna di destinazione anziché quella predefinita per i tipi <code>VARCHAR</code> e <code>CHAR</code>. Questa modifica elimina la possibilità di danneggiamento dei dati causata dall'uso della codifica predefinita quando questa non viene usata dalla colonna di destinazione. In rari casi, un'applicazione esistente può generare un'eccezione SqlException se la modifica nella codifica produce dati troppo grandi per rientrare nella colonna di destinazione.|
|Suggerimento|<xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=name> non danneggerà più i dati a causa di differenze di codifica. Se vengono copiate stringhe prossime al limite delle dimensioni della colonna di destinazione, può essere necessario pre-codificare i dati (copiarli per verificare che rientrino nella colonna di destinazione) o rilevare eccezioni <xref:System.Data.SqlClient.SqlException?displayProperty=name>.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)?displayProperty=nameWithType></li></ul>|

