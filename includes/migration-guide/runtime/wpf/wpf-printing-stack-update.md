### <a name="wpf-printing-stack-update"></a>Aggiornamento dello stack di stampa WPF

|   |   |
|---|---|
|Dettagli|Le API di stampa di WPF che usano <xref:System.Printing.PrintQueue?displayProperty=name> ora chiamano l'API di gestione del pacchetto dei documenti di stampa di Windows invece dell'API di stampa XPS, ora deprecata. La modifica è stata apportata per ottimizzare la funzionalità. Né gli utenti né gli sviluppatori dovrebbero riscontrare modifiche nel comportamento o nell'uso dell'API. Il nuovo stack di stampa viene abilitato per impostazione predefinita durante l'esecuzione in Windows 10 Creators Update. Il vecchio stack di stampa continua a funzionare come in precedenza nelle versioni precedenti di Windows.|
|Suggerimento|Per usare lo stack precedente in Windows 10 Creators Update, impostare il valore <code>UseXpsOMPrinting</code> REG_DWORD della chiave del Registro di sistema <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> su <code>1</code>.|
|Ambito|Microsoft Edge|
|Versione|4.7|
|Tipo|Runtime|

