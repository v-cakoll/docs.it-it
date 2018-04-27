### <a name="path-colon-checks-are-stricter"></a>I controlli della presenza di due punti nel percorso sono più severi

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6.2 sono state apportate varie modifiche per supportare i percorsi in precedenza non supportati (sia per lunghezza che per formato). I controlli della sintassi corretta del separatore appropriato per le unità (due punti) sono ora più corretti. L'effetto collaterale è però il blocco di alcuni percorsi URI in un gruppo selezionato di API Path in cui l'uso era tollerato.|
|Suggerimento|Per il passaggio di un URI alle API interessate, modificare prima di tutto la stringa in modo che sia un percorso valido.<ul><li>Rimuovere manualmente lo schema dagli URL (ad esempio rimuovere <code>file://</code> dagli URL)</li><li>Passare l'URI alla classe <xref:System.Uri> e usare <xref:System.Uri.LocalPath></li></ul>In alternativa, è possibile rifiutare esplicitamente la nuova normalizzazione dei percorsi impostando l'opzione di AppContext <code>Switch.System.IO.UseLegacyPathHandling</code> su true.|
|Ambito|Microsoft Edge|
|Versione|4.6.2|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType></li><li><xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType></li></ul>|

