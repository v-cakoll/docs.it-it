### <a name="applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>Application.FilterMessage non genera più un'eccezione per le implementazioni rientranti di IMessageFilter.PreFilterMessage

|   |   |
|---|---|
|Dettagli|Prima di .NET Framework 4.6.1, la chiamata di <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> con <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> che comportava la chiamata di <xref:System.Windows.Forms.Application.AddMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=name> o <xref:System.Windows.Forms.Application.RemoveMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=name> (chiamando anche <xref:System.Windows.Forms.Application.DoEvents>) avrebbe causato <xref:System.IndexOutOfRangeException?displayProperty=name>. A partire dalle applicazioni destinate a .NET Framework 4.6.1, questa eccezione non viene più generata e si possono usare filtri rientranti come descritto in precedenza.|
|Suggerimento|Tenere presente che <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> non genererà più un'eccezione per il comportamento <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> rientrante descritto in precedenza. Questa condizione influisce solo sulle applicazioni destinate a .NET Framework 4.6.1. Le app destinate a .NET Framework 4.6.1 possono rifiutare esplicitamente questa modifica (o le app destinate a versioni precedenti possono acconsentire esplicitamente) usando l'opzione di compatibilità [DontSupportReentrantFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md#mitigation).|
|Ambito|Microsoft Edge|
|Versione|4.6.1|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)?displayProperty=nameWithType></li></ul>|

