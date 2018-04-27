### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Lo stato della sessione di condivisione con Asp.Net StateServer richiede che tutti i server nella Web farm usino la stessa versione di .NET Framework

|   |   |
|---|---|
|Dettagli|Quando si abilita lo stato della sessione <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name>, tutti i server nella Web farm specificata devono usare la stessa versione di .NET Framework affinché lo stato venga condiviso correttamente.|
|Suggerimento|Verificare di aggiornare le versioni di .NET Framework nei server Web che condividono lo stato nello stesso momento.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|

