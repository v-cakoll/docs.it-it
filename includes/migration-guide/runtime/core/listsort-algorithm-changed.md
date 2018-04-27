### <a name="listsort-algorithm-changed"></a>L'algoritmo List.Sort è stato modificato

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5, l'algoritmo di ordinamento di <xref:System.Collections.Generic.List%601?displayProperty=name> è stato modificato in ordinamento introspettivo anziché ordinamento rapido. L'ordinamento di <xref:System.Collections.Generic.List%601?displayProperty=name> non è mai stato stabile, ma questa modifica potrebbe determinare un ordinamento instabile in scenari diversi. Ciò significa semplicemente che l'ordinamento di elementi equivalenti potrebbe risultare diverso nelle successive chiamate dell'API.|
|Suggerimento|Poiché anche l'algoritmo di ordinamento precedente era instabile, anche se in modi leggermente diversi, nessun codice deve dipendere da elementi equivalenti sempre ordinati in un particolare ordine. In presenza di istanze di codice con questo tipo di dipendenza che funzionano correttamente con il vecchio comportamento, è necessario aggiornare il codice in modo che usi un operatore di confronto che ordinerà gli elementi in modo deterministico nell'ordine desiderato.|
|Ambito|Trasparente|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Collections.Generic.List%601.Sort?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Comparison{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li></ul>|

