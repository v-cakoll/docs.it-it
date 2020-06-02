---
title: Comando dotnet test
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
ms.date: 04/29/2020
ms.openlocfilehash: 1190ecb75e83c9930c60726e7cd83203b11928cb
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283936"
---
# <a name="dotnet-test"></a>dotnet test

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet test`: driver di test .NET usato per eseguire gli unit test.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL>]
    [-a|--test-adapter-path <PATH_TO_ADAPTER>] [--blame]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_FRIENDLY_NAME>]
    [-d|--diag <PATH_TO_DIAGNOSTICS_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER_URI/FRIENDLY_NAME>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <PATH>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a>Descrizione

Il `dotnet test` comando viene usato per eseguire unit test in una determinata soluzione. Il `dotnet test` comando Compila la soluzione ed esegue un'applicazione host di test per ogni progetto di test nella soluzione. L'host di test esegue i test nel progetto specificato utilizzando un Framework di test, ad esempio MSTest, NUnit o xUnit, e segnala l'esito positivo o negativo di ogni test. Se tutti i test hanno esito positivo, il test runner restituisce 0 come codice di uscita. Se invece i test hanno esito negativo, restituisce 1.

Per i progetti multitargeting, i test vengono eseguiti per ogni Framework di destinazione. L'host di test e il framework unit test vengono inclusi nel pacchetto come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.

I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

Dove `Microsoft.NET.Test.Sdk` è l'host di test, `xunit` è il Framework di test. E `xunit.runner.visualstudio` è un adattatore di test, che consente al Framework xUnit di funzionare con l'host di test.

### <a name="implicit-restore"></a>Ripristino implicito

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a>Argomenti

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - Percorso del progetto di test.
  - Percorso della soluzione.
  - Percorso di una directory che contiene un progetto o una soluzione.
  - Percorso di un file con estensione *dll* del progetto di test.

  Se non specificato, Cerca un progetto o una soluzione nella directory corrente.

## <a name="options"></a>Opzioni

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  Percorso di una directory in cui eseguire la ricerca di altri adattatori di test. Vengono controllati solo i file con *estensione dll* con suffisso `.TestAdapter.dll` . Se non specificato, viene eseguita una ricerca nella directory della *dll* test.

- **`--blame`**

  Esegue i test in modalità di segnalazione degli errori. Questa opzione è utile per isolare i test problematici che provocano l'arresto anomalo dell'host di test. Quando viene rilevato un arresto anomalo del sistema, viene creato un file di sequenza in `TestResults/<Guid>/<Guid>_Sequence.xml` che acquisisce l'ordine dei test eseguiti prima dell'arresto anomalo.

- **`-c|--configuration <CONFIGURATION>`**

  Definisce la configurazione di compilazione. Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  Abilita l'agente di raccolta dati per l'esecuzione dei test. Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).
  
  Per raccogliere code coverage su qualsiasi piattaforma supportata da .NET Core, installare [copriletto](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) e usare l' `--collect:"XPlat Code Coverage"` opzione.

  In Windows è possibile raccogliere code coverage utilizzando l' `--collect "Code Coverage"` opzione. Questa opzione genera un file con *estensione coverage* , che può essere aperto in Visual Studio 2019 Enterprise. Per ulteriori informazioni, vedere [utilizzare code coverage](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) e [personalizzare code coverage analysis](/visualstudio/test/customizing-code-coverage-analysis).

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato e nei file accanto. Il processo che registra i messaggi determina quali file vengono creati, ad esempio `*.host_<date>.txt` per il log dell'host di test e `*.datacollector_<date>.txt` per il log dell'agente di raccolta dati.

- **`-f|--framework <FRAMEWORK>`**

  Impone l'uso di `dotnet` o .NET Framework host di test per i file binari del test. Questa opzione determina solo il tipo di host da usare. La versione effettiva del Framework da usare è determinata da *runtimeconfig. JSON* del progetto di test. Quando non è specificato, viene usato l' [attributo dell'assembly TargetFramework](/dotnet/api/system.runtime.versioning.targetframeworkattribute) per determinare il tipo di host. Quando tale attributo viene rimosso dal file con *estensione dll*, viene utilizzato l'host .NET Framework.

- **`--filter <EXPRESSION>`**

  Filtra i test nel progetto corrente usando l'espressione specificata. Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details). Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente, ad esempio il completamento dell'autenticazione. Disponibile a partire da .NET Core 3.0 SDK.

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  Specifica un logger per i risultati di test. Diversamente da MSBuild, il test DotNet non accetta abbreviazioni: invece di `-l "console;v=d"` usare `-l "console;verbosity=detailed"` .

- **`--no-build`**

  Non compila il progetto di test prima dell'esecuzione. Viene inoltre impostato in modo implicito il `--no-restore` flag-.

- **`--nologo`**

  Esegui test senza visualizzare il banner Microsoft TestPlatform. Disponibile a partire da .NET Core 3.0 SDK.

- **`--no-restore`**

  Non esegue un ripristino implicito quando si esegue il comando.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Directory in cui trovare i file binari da eseguire. Se non specificata, il percorso predefinito è `./bin/<configuration>/<framework>/`.  Per i progetti con più framework di destinazione (tramite la `TargetFrameworks` proprietà), è necessario definire anche `--framework` quando si specifica questa opzione. `dotnet test`esegue sempre i test dalla directory di output. È possibile usare <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> per utilizzare gli asset di test nella directory di output.

- **`-r|--results-directory <PATH>`**

  Directory in cui verranno inseriti i risultati del test. Se la directory specificata non esiste, viene creata. Il valore predefinito è `TestResults` la directory che contiene il file di progetto.

- **`--runtime <RUNTIME_IDENTIFIER>`**

  Runtime di destinazione di cui eseguire il test.

- **`-s|--settings <SETTINGS_FILE>`**

  Il file `.runsettings` da usare per l'esecuzione dei test. L' `TargetPlatform` elemento (x86 | x64) non ha alcun effetto per `dotnet test` . Per eseguire test destinati a x86, installare la versione x86 di .NET Core. Il bit di *dotnet. exe* che si trova nel percorso è quello che verrà usato per l'esecuzione dei test. Per altre informazioni, vedere le seguenti risorse:

  - [Configurare unit test usando un file `.runsettings`.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [Configurare un agente di test](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  Elenca tutti i test individuati nel progetto corrente.

- **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `minimal`. Per altre informazioni, vedere <xref:Microsoft.Build.Framework.LoggerVerbosity>.

- **`RunSettings`** argomenti

 Inline `RunSettings` vengono passati come ultimi argomenti nella riga di comando dopo "--" (si noti lo spazio dopo--). Inline `RunSettings` sono specificati come `[name]=[value]` coppie. Per separare più coppie `[name]=[value]`, viene usato uno spazio.

  Esempio: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`

  Per ulteriori informazioni, vedere [passaggio di argomenti runsettings tramite la riga di comando](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).

## <a name="examples"></a>Esempi

- Eseguire i test nel progetto nella directory corrente:

  ```dotnetcli
  dotnet test
  ```

- Eseguire i test nel progetto `test1`:

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- Eseguire i test nel progetto nella directory corrente e generare un file dei risultati del test nel formato TRX:

  ```dotnetcli
  dotnet test --logger trx
  ```

- Eseguire i test nel progetto nella directory corrente e generare un file di code coverage (dopo l'installazione di [copriletto](https://github.com/tonerdo/coverlet/blob/master/README.md)):

  ```dotnetcli
  dotnet test --collect:"XPlat Code Coverage"
  ```

- Eseguire i test nel progetto nella directory corrente e generare un file di code coverage (solo Windows):

  ```dotnetcli
  dotnet test --collect "Code Coverage"
  ```

- Eseguire i test nel progetto nella directory corrente e accedere con un livello di dettaglio dettagliato alla console:

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```
  
  - Eseguire i test nel progetto nella directory corrente e segnalare i test in corso quando l'host di test si è arrestato in modo anomalo:

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a>Dettagli dell'opzione filter

`--filter <EXPRESSION>`

`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.

`<property>` è un attributo di `Test Case`. La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:

| Framework di test | Proprietà supportate                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>Nome</li><li>ClassName</li><li>Priorità</li><li>TestCategory</li></ul> |
| xUnit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>Tratti</li></ul>                                   |
| NUnit          | <ul><li>FullyQualifiedName</li><li>Nome</li><li>TestCategory</li><li>Priorità</li></ul>                                   |

`<operator>` descrive la relazione tra la proprietà e il valore:

| Operatore | Funzione        |
| :------: | --------------- |
| `=`      | Corrispondenza esatta     |
| `!=`     | Corrispondenza non esatta |
| `~`      | Contiene        |
| `!~`     | Non contiene    |

`<value>` è una stringa. Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.

Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.

Le espressioni possono essere unite con operatori condizionali:

| Operatore            | Funzione |
| ------------------- | -------- |
| <code>&#124;</code> | OR       |
| `&`                 | AND      |

È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).

Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).

## <a name="see-also"></a>Vedere anche

- [Framework e destinazioni](../../standard/frameworks.md)
- [Catalogo dei RID (Runtime IDentifier) di .NET Core](../rid-catalog.md)
- [Passaggio di argomenti runsettings tramite la riga di comando](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
