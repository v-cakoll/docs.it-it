---
title: Comando dotnet test
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
ms.date: 04/29/2020
ms.openlocfilehash: a8218b6596601069b89a60ad018adf89a1f47cf6
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624891"
---
# <a name="dotnet-test"></a>dotnet test

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet test`: driver di test .NET usato per eseguire gli unit test.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
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

Il comando `dotnet test` viene usato per eseguire unit test in un determinato progetto. Il comando `dotnet test` avvia l'applicazione console di esecuzione dei test specificati per un progetto. L'applicazione di esecuzione dei test esegue i test definiti per un framework di unit test (ad esempio MSTest, NUnit o xUnit) e segnala l'esito positivo o negativo di ogni test. Se tutti i test hanno esito positivo, il test runner restituisce 0 come codice di uscita. Se invece i test hanno esito negativo, restituisce 1. Per i progetti multitargeting, i test vengono eseguiti per ogni Framework di destinazione. L'applicazione di esecuzione dei test e la libreria di unit test sono disponibili come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.

I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

### <a name="implicit-restore"></a>Ripristino implicito

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a>Argomenti

- **`PROJECT | SOLUTION`**

  Percorso del progetto o della soluzione di test. Se non specificato, per impostazione predefinita viene usata la directory corrente.

## <a name="options"></a>Opzioni

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.

- **`--blame`**

  Esegue i test in modalità di segnalazione degli errori. Questa opzione è utile per isolare i test problematici che provocano l'arresto anomalo dell'host di test. Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.

- **`-c|--configuration <CONFIGURATION>`**

  Definisce la configurazione di compilazione. Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  Abilita l'agente di raccolta dati per l'esecuzione dei test. Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.

- **`-f|--framework <FRAMEWORK>`**

  Cerca i file binari di test per un [Framework](../../standard/frameworks.md)specifico.

- **`--filter <EXPRESSION>`**

  Filtra i test nel progetto corrente usando l'espressione specificata. Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details). Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente, ad esempio il completamento dell'autenticazione. Disponibile a partire da .NET Core 3.0 SDK.

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  Specifica un logger per i risultati di test. Diversamente da MSBuild, il test DotNet non accetta abbreviazioni: invece `-l "console;v=d"` di `-l "console;verbosity=detailed"`usare.

- **`--no-build`**

  Non compila il progetto di test prima dell'esecuzione. Viene inoltre impostato in modo implicito `--no-restore` il flag-.

- **`--nologo`**

  Esegui test senza visualizzare il banner Microsoft TestPlatform. Disponibile a partire da .NET Core 3.0 SDK.

- **`--no-restore`**

  Non esegue un ripristino implicito quando si esegue il comando.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Directory in cui trovare i file binari da eseguire. Se non specificata, il percorso predefinito è `./bin/<configuration>/<framework>/`.  Per i progetti con più framework di destinazione (tramite `TargetFrameworks` la proprietà), è necessario definire `--framework` anche quando si specifica questa opzione. `dotnet test`eseguire sempre i test dalla directory di output. È possibile usare <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> per utilizzare gli asset di test nella directory di output.

- **`-r|--results-directory <PATH>`**

  Directory in cui verranno inseriti i risultati del test. Se la directory specificata non esiste, viene creata. Il valore predefinito `TestResults` è la directory che contiene il file di progetto.

- **`--runtime <RUNTIME_IDENTIFIER>`**

  Runtime di destinazione di cui eseguire il test.

- **`-s|--settings <SETTINGS_FILE>`**

  Il file `.runsettings` da usare per l'esecuzione dei test. Si noti che `TargetPlatform` l'elemento (x86 | x64) non ha alcun `dotnet test`effetto per. Per eseguire test destinati a x86, installare la versione x86 di .NET Core. Il bit di *dotnet. exe* che si trova nel percorso è quello che verrà usato per l'esecuzione dei test. Per ulteriori informazioni, vedere le risorse seguenti:

  - [Configurare unit test usando un file `.runsettings`.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [Configurare un agente di test](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  Elenca tutti i test individuati nel progetto corrente.

- **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `minimal`. Per altre informazioni, vedere <xref:Microsoft.Build.Framework.LoggerVerbosity>.

- **`RunSettings`** argomenti

  Gli argomenti vengono passati `RunSettings` come configurazioni per il test. Gli argomenti vengono specificati come coppie `[name]=[value]` dopo "-- ". Si noti lo spazio dopo --. Per separare più coppie `[name]=[value]`, viene usato uno spazio.

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

- Eseguire i test nel progetto nella directory corrente e accedere con un livello di dettaglio dettagliato alla console:

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a>Dettagli dell'opzione filter

`--filter <EXPRESSION>`

`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.

`<property>` è un attributo di `Test Case`. La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:

| Framework di test | Proprietà supportate                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>Nome</li><li>ClassName</li><li>Priorità</li><li>TestCategory</li></ul> |
| xUnit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>Tratti</li></ul>                                   |

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
