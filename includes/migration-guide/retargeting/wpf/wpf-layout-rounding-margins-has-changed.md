### <a name="wpf-layout-rounding-of-margins-has-changed"></a>L'arrotondamento del layout dei margini in WPF è stato modificato

|   |   |
|---|---|
|Dettagli|Il modo in cui i margini vengono arrotondati e i bordi e lo sfondo al loro interno vengono modificati. Come conseguenza di questo cambiamento:<ul><li>La larghezza o l'altezza degli elementi può aumentare o diminuire al massimo di un pixel.</li><li>La posizione di un oggetto può cambiare al massimo di un pixel.</li><li>Gli elementi centrati possono risultare decentrati in orizzontale o in verticale al massimo di un pixel.</li></ul>Per impostazione predefinita, questo nuovo layout è disponibile solo per app destinate a .NET Framework 4.6.|
|Suggerimento|Poiché questa modifica tende a eliminare il ritaglio del lato destro o inferiore dei controlli WPF a DPI elevati, le app destinate a versioni precedenti di .NET Framework ma eseguite su .NET Framework 4.6 possono adottare questo nuovo comportamento aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config: <code>&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;</code>. Le app destinate a .NET Framework 4.6 ma che richiedono che il rendering dei controlli WPF venga eseguito mediante l'algoritmo di layout precedente possono aggiungere a questo scopo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config: <code>&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;</code>.|
|Ambito|Secondario|
|Versione|4.6|
|Tipo|Ridestinazione|

