### <a name="targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>L'impostazione predefinita di TargetFrameworkName per il dominio app predefinito non è più Null, se non impostata

|   |   |
|---|---|
|Dettagli|<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=name> era precedentemente Null nel dominio app predefinito, se non impostata in modo esplicito. A partire dalla versione 4.6, la proprietà <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=name> per il dominio app predefinito avrà un valore predefinito derivato da TargetFrameworkAttribute, se presente. I domini app non predefiniti continueranno a ereditare la proprietà <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=name> dal dominio app predefinito (che non avrà per impostazione predefinita il valore Null nella versione 4.6), a meno che non sia sottoposta a override in modo esplicito.|
|Suggerimento|Il codice deve essere aggiornato in modo che non dipenda dal fatto che l'impostazione predefinita di <xref:System.AppDomainSetup.TargetFrameworkName> sia null. Se è necessario che questa proprietà continui a restituire null, è possibile impostarla in modo esplicito su tale valore.|
|Ambito|Microsoft Edge|
|Versione|4.6|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=nameWithType></li></ul>|

