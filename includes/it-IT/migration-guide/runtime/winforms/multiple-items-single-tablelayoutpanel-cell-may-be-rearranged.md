### <a name="multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>Più elementi possono essere riorganizzati in una singola cella di TableLayoutPanel

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5 più elementi inseriti nella stessa cella di <xref:System.Windows.Forms.TableLayoutPanel?displayProperty=name> possono apparire in un ordine diverso rispetto a .NET Framework 4.0.|
|Suggerimento|Questo comportamento è stato ripristinato in un aggiornamento di manutenzione per .NET Framework 4.5. Per risolvere questo problema, aggiornare .NET Framework 4.5 o eseguire l'aggiornamento a .NET Framework 4.5.1 o versioni successive. In alternativa, evitare il caso ambiguo di più elementi nella stessa cella di <xref:System.Windows.Forms.TableLayoutPanel?displayProperty=name>.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Forms.TableLayoutControlCollection.Add(System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32)?displayProperty=nameWithType></li></ul>|
|Analizzatori|<ul><li>CD0098</li></ul>|

