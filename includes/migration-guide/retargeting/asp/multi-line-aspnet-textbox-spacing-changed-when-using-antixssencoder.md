### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>Modifica della spaziatura nel controllo TextBox ASP.Net multiriga quando si usa AntiXSSEncoder

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.0 vengono inserite righe aggiuntive tra le righe di una casella di testo a più righe durante il postback, se si usa <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name>. In .NET Framework 4.5 queste interruzioni di riga aggiuntive non vengono incluse, ma solo se l'app Web è destinata a .NET 4.5|
|Suggerimento|Tenere presente che nelle app Web 4.0 ridestinate a .NET 4.5, le caselle di testo a più righe possono essere migliorate in modo che non vengano più inserite interruzioni di riga aggiuntive. Se non è opportuno, l'app può avere il comportamento precedente quando viene eseguita in .NET Framework 4.5 usando .NET Framework 4.0 come destinazione.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Ridestinazione|

