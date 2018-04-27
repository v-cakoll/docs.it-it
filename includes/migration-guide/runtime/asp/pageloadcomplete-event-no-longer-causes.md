### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>L'evento Page.LoadComplete non causa più la chiamata al data binding da parte del controllo System.Web.UI.WebControls.EntityDataSource

|   |   |
|---|---|
|Dettagli|L'evento <xref:System.Web.UI.Page.LoadComplete> non determina più la chiamata all'associazione dati da parte del controllo <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=name> per modifiche ai parametri di creazione/aggiornamento/eliminazione. Questa modifica determina l'eliminazione di un accesso estraneo al database, impedisce la reimpostazione dei valori dei controlli e genera un comportamento coerente con altri controlli di dati, quali <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=name> e <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=name>. Questa modifica determina un comportamento diverso nel caso improbabile in cui le applicazioni si affidino al richiamo dell'associazione dati nell'evento <xref:System.Web.UI.Page.LoadComplete>.|
|Suggerimento|Se il data binding è necessario, richiamare manualmente databind in un evento in una posizione precedente nel postback.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|

