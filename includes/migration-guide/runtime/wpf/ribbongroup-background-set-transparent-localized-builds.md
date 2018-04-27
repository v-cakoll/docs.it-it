### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>Viene impostato lo sfondo trasparente per RibbonGroup nelle build localizzate

|   |   |
|---|---|
|Dettagli|Lo sfondo di <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> nelle build localizzate viene sempre disegnato con il pennello trasparente, causando un'esperienza insoddisfacente per l'interfaccia utente. Questo problema è stato risolto nella correzione WPF per .NET 4.7 con l'aggiornamento delle risorse localizzate per <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, che a sua volta garantisce che sia selezionato il pennello corretto.|
|Suggerimento|Eseguire l'aggiornamento a .NET 4.7|
|Ambito|Microsoft Edge|
|Versione|4.6.2|
|Tipo|Runtime|

