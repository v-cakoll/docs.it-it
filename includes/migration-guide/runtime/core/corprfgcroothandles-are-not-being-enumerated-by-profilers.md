### <a name="corprfgcroothandles-are-not-being-enumerated-by-profilers"></a>Gli COR_PRF_GC_ROOT_HANDLE non vengono enumerati dai profiler

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5.1, l'API di profilatura <code>RootReferences2()</code> non restituisce mai <code>COR_PRF_GC_ROOT_HANDLE</code> erroneamente (vengono invece restituiti come <code>COR_PRF_GC_ROOT_OTHER</code>). Questo problema è risolto a partire da .NET Framework 4.6.|
|Suggerimento|Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.|
|Ambito|Secondario|
|Versione|4.5.1|
|Tipo|Runtime|

