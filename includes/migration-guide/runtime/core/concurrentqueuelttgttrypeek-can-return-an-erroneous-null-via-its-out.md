### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue&lt;T&gt;.TryPeek può restituire erroneamente un valore Null tramite il parametro di output

|   |   |
|---|---|
|Dettagli|In alcuni scenari multithread, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> può restituire true, ma popolare il parametro di output con un valore null, anziché il valore corretto, restituito.|
|Suggerimento|Questo problema è risolto in .NET Framework 4.5.1. L'aggiornamento a questa versione di .NET Framework consentirà di risolvere il problema.|
|Ambito|Principale|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|

