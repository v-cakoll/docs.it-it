### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a>RSACng.VerifyHash ora restituisce False per qualsiasi errore di verifica

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6.2, questo metodo restituisce <strong>False</strong> se la firma stessa non è formattata correttamente. Ora restituisce false per qualsiasi errore di verifica. In .NET Framework 4.6 e 4.6.1, il metodo genera <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> se non è formattata correttamente la firma stessa.|
|Suggerimento|Qualsiasi codice la cui esecuzione dipenda da <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> deve invece essere eseguito se la convalida non va a buon fine e il metodo restituisce <strong>False</strong>.|
|Ambito|Secondario|
|Versione|4.6.2|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|

