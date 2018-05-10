### <a name="entity-framework-version-must-match-the-net-framework-version"></a>La versione di Entity Framework deve corrispondere alla versione di .NET Framework

|   |   |
|---|---|
|Dettagli|La versione di Entity Framework deve corrispondere alla versione di .NET Framework. Per .NET Framework 4.5 è consigliato Entity Framework 5. Esistono alcuni problemi noti con Entity Framework 4.x in un progetto .NET Framework 4.5 in relazione a <xref:System.ComponentModel.DataAnnotations>. In .NET 4.5, questi elementi sono stati spostati in un assembly diverso, pertanto vi sono problemi a determinare quali annotazioni usare.|
|Suggerimento|Eseguire l'aggiornamento a Entity Framework 5 per .NET Framework 4.5|
|Ambito|Principale|
|Versione|4.5|
|Tipo|Ridestinazione|

