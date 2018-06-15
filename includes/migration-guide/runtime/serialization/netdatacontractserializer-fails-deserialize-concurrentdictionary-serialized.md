### <a name="netdatacontractserializer-fails-to-deserialize-a-concurrentdictionary-serialized-with-a-different-net-version"></a>NetDataContractSerializer non riesce a deserializzare un elemento ConcurrentDictionary serializzato con una versione di .NET diversa

|   |   |
|---|---|
|Dettagli|Come da progettazione, la classe <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> può essere usata solo se le estremità di serializzazione e deserializzazione condividono gli stessi tipi CLR. La deserializzazione di un oggetto serializzato con una versione di .NET Framework da parte di una versione diversa non è quindi garantita. <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name> è un tipo che non viene deserializzato correttamente se serializzato con .NET Framework 4.5 o versioni precedenti e deserializzato con .NET Framework 4.5.1 o versioni successive.|
|Suggerimento|Per risolvere questo problema, sono disponibili alcune soluzioni alternative:<ul><li>Aggiornare anche il computer di serializzazione a .NET Framework 4.5.1.</li><li>Usare <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> anziché <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> poiché non prevede esattamente gli stessi tipi CLR a entrambe le estremità di serializzazione e deserializzazione.</li><li>Usare <xref:System.Collections.Generic.Dictionary%602?displayProperty=name> anziché <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name> poiché non mostra questo particolare problema 4.5-&gt;4.5.1.</li></ul>|
|Ambito|Secondario|
|Versione|4.5.1|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li></ul>|

