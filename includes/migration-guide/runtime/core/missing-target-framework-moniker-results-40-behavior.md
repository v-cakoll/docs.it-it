### <a name="missing-target-framework-moniker-results-in-40-behavior"></a>Comportamento 4.0 a causa della mancanza del moniker del framework di destinazione

|   |   |
|---|---|
|Dettagli|Le applicazioni senza un <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> applicato a livello di assembly verranno eseguite automaticamente con la semantica (non standard) di .NET Framework 4.0. Per garantire un livello di qualità elevato, è consigliabile applicare a tutti i file binari in modo esplicito un attributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> che indica la versione di .NET Framework con cui sono stati compilati. Si noti che l'uso di un moniker del framework di destinazione in un file di progetto causerà l'applicazione automatica di un <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> da MSBuild.|
|Suggerimento|È consigliabile specificare un <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> aggiungendo direttamente l'attributo all'assembly oppure specificando un framework di destinazione nel [file di progetto o tramite l'interfaccia utente grafica delle proprietà del progetto di Visual Studio](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio- managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx).|
|Ambito|Principale|
|Versione|4.5|
|Tipo|Runtime|

