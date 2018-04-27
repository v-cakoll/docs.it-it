### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a>L'impostazione MinFreeMemoryPercentageToActiveService viene ora rispettata

|   |   |
|---|---|
|Dettagli|Questa impostazione consente di stabilire la quantità minima di memoria che deve essere disponibile nel server per poter attivare un servizio WCF. È progettata in modo da prevenire le eccezioni <xref:System.OutOfMemoryException?displayProperty=name>. In .NET Framework 4.5 questa impostazione non ha alcun effetto. In .NET Framework 4.5.1 questa impostazione viene applicata.|
|Suggerimento|Viene generata un'eccezione se la quantità di memoria libera disponibile sul server Web è inferiore alla percentuale definita dall'impostazione di configurazione. Alcuni servizi WCF correttamente avviati ed eseguiti in un ambiente di memoria limitato potrebbero avere esito negativo.|
|Ambito|Secondario|
|Versione|4.5.1|
|Tipo|Runtime|

