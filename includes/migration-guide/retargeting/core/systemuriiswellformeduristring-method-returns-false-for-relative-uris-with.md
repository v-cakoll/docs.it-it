### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a>Il metodo System.Uri.IsWellFormedUriString restituisce false per gli URI relativi con un carattere due punti nel primo segmento

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5, <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> tratterà gli URI relativi con <code>:</code> nella primo segmento come non ben formati. Si tratta di una modifica rispetto al comportamento di <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=name> in .NET Framework 4.0, introdotta per conformarsi a RFC3986.|
|Suggerimento|Questa modifica (come molte altre modifiche relative agli URI) influirà solo sulle applicazioni destinate a .NET Framework 4.5 o versioni successive. Per continuare a usare il comportamento precedente, scegliere .NET Framework 4.0 come destinazione dell'app. In alternativa, analizzare l'URI prima di chiamare <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=name> per cercare caratteri <code>:</code> che è possibile rimuovere ai fini della convalida, se si desidera mantenere il comportamento precedente.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType></li></ul>|

