### <a name="xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>La convalida di XSD Schema ora rileva correttamente le violazioni dei vincoli univoci se vengono usate chiavi composte e una chiave è vuota

|   |   |
|---|---|
|Dettagli|Le versioni di .NET Framework precedenti alla 4.6 includono un bug a causa del quale la convalida XSD non rileva vincoli univoci per le chiavi composte se una delle chiavi è vuota. Questo problema è stato corretto in .NET Framework 4.6. La convalida sarà più corretta, ma è possibile che la convalida di alcuni file XML abbia esito negativo, diversamente da quanto accadeva in precedenza.|
|Suggerimento|Se è necessario usare la convalida .NET Framework 4.0 meno restrittiva, l'applicazione da convalidare può essere destinata alla versione 4.5 (o versioni precedenti) di .NET Framework. In caso di ridestinazione alla versione .NET 4.6, tuttavia, è necessario rivedere il codice per assicurarsi che non sia prevista la convalida per le chiavi composte duplicate, come descritto nella descrizione di questo problema.|
|Ambito|Microsoft Edge|
|Versione|4.6|
|Tipo|Ridestinazione|

