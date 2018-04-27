### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>PreviewLostKeyboardFocus viene chiamato ripetutamente se il gestore visualizza una finestra di messaggio di Windows Forms

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5, la chiamata di <code>System.Windows.Forms.MessageBox.Show</code> da un gestore <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> causerà la riattivazione del gestore alla chiusura della finestra di messaggio, con un potenziale ciclo infinito di finestre di messaggio.|
|Suggerimento|Esistono due modi per risolvere l'errore:<ol><li>Può essere evitato chiamando <code>System.Windows.MessageBox.Show</code> invece di <code>System.Windows.Forms.MessageBox.Show</code>.</li><li>Può essere evitato visualizzando la finestra di messaggio da un gestore eventi <xref:System.Windows.UIElement.LostKeyboardFocus>, anziché un gestore eventi <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=name>.</li></ol>|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType></li></ul>|

