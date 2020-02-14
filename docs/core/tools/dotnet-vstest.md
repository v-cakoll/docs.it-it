---
title: Comando dotnet vstest
description: Il comando dotnet vstest consente di compilare un progetto e tutte le relative dipendenze.
ms.date: 05/30/2018
ms.openlocfilehash: c3838617ed539cf56f2840b826e9de58833820fd
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215303"
---
# <a name="dotnet-vstest"></a>dotnet vstest

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Nome

`dotnet-vstest`: esegue test dai file specificati.

## <a name="synopsis"></a>Riepilogo

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [--Blame|/Blame] [--InIsolation|/InIsolation]
    [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] 
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] 
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

---

## <a name="description"></a>Descrizione

Il comando `dotnet-vstest` esegue l'applicazione della riga di comando `VSTest.Console` per eseguire unit test automatizzati.

## <a name="arguments"></a>Argomenti

`TEST_FILE_NAMES`

Eseguire i test dagli assembly specificati. Per separare più nomi di assembly di test, usare gli spazi.

## <a name="options"></a>Opzioni

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--Settings|/Settings:<Settings File>`

Impostazioni da usare durante l'esecuzione di test.

`--Tests|/Tests:<Test Names>`

Esegue test con nomi corrispondenti ai valori specificati. Se si specificano più valori, separarli con virgole.

`--TestAdapterPath|/TestAdapterPath`

Durante l'esecuzione dei test, vengono usati adattatori di test personalizzati da un percorso specificato (se presenti).

`--Platform|/Platform:<Platform type>`

Architettura della piattaforma di destinazione usata per l'esecuzione dei test. I valori validi sono `x86`, `x64` e `ARM`.

`--Framework|/Framework:<Framework Version>`

Versione di .NET Framework di destinazione usata per l'esecuzione dei test. Esempi di valori validi sono `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`. Altri valori supportati sono `Framework40`, `Framework45`, `FrameworkCore10` e `FrameworkUap10`.

`--Parallel|/Parallel`

Esegue test in parallelo. Per impostazione predefinita, tutti i core presenti nel computer sono disponibili per l'uso. Specificare un numero esplicito di core impostando la proprietà MaxCpuCount nel nodo RunConfiguration nel file runsettings.

`--TestCaseFilter|/TestCaseFilter:<Expression>`

Esegue test corrispondenti all'espressione specificata. `<Expression>` è in formato `<property>Operator<value>[|&<Expression>]`, dove Operator è `=`, `!=` o `~`. L'operatore `~` usa la semantica 'contains' ed è applicabile per le proprietà stringa come `DisplayName`. Per raggruppare le sottoespressioni vengono usate le parentesi `()`.

`-?|--Help|/?|/Help`

Stampa una breve guida per il comando.

`--logger|/logger:<Logger Uri/FriendlyName>`

Specifica un logger per i risultati dei test.

* Per pubblicare i risultati dei test in Team Foundation Server, usare il provider di logger `TfsPublisher`:

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* Per registrare i risultati in un file di risultati dei test di Visual Studio (con estensione trx), usare il provider di logger `trx`. Questa opzione crea un file nella directory dei risultati dei test con nome di file di log specificato. Se `LogFileName` non è specificato, viene creato un nome di file univoco per contenere i risultati dei test.

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

Elenca tutti i test individuati dal contenitore di test specificato.

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

ID del processo padre responsabile dell'avvio del processo corrente.

`--Port|/Port:<Port>`

Specifica la porta per la connessione socket e la ricezione dei messaggi di evento.

`--Diag|/Diag:<Path to log file>`

Abilita i log dettagliati per la piattaforma di test. I log vengono scritti nel file specificato.

`--Blame|/Blame`

Esegue i test in modalità di segnalazione degli errori. Questa opzione è utile per isolare i test problematici che causano un arresto anomalo dell'host dei test. Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.

`--InIsolation|/InIsolation`

Esegue i test in un processo isolato. In questo modo si riduce la probabilità di arresto del processo di *vstest.console.exe* a causa di un errore durante i test, sebbene questi ultimi potrebbero risultare più lenti.

`@<file>`

Legge un file di risposta per altre opzioni.

`args`

Specifica argomenti aggiuntivi da passare all'adattatore. Gli argomenti sono specificati come coppie nome-valore nel formato `<n>=<v>`, dove `<n>` è il nome dell'argomento e `<v>` è il valore dell'argomento. Per separare più argomenti usare uno spazio.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--Settings|/Settings:<Settings File>`

Impostazioni da usare durante l'esecuzione di test.

`--Tests|/Tests:<Test Names>`

Esegue test con nomi corrispondenti ai valori specificati. Se si specificano più valori, separarli con virgole.

`--TestAdapterPath|/TestAdapterPath`

Durante l'esecuzione dei test, vengono usati adattatori di test personalizzati da un percorso specificato (se presenti).

`--Platform|/Platform:<Platform type>`

Architettura della piattaforma di destinazione usata per l'esecuzione dei test. I valori validi sono `x86`, `x64` e `ARM`.

`--Framework|/Framework:<Framework Version>`

Versione di .NET Framework di destinazione usata per l'esecuzione dei test. Esempi di valori validi sono `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`. Altri valori supportati sono `Framework40`, `Framework45` e `FrameworkCore10`.

`--Parallel|/Parallel`

Esegue test in parallelo. Per impostazione predefinita, tutti i core presenti nel computer sono disponibili per l'uso. Specificare un numero esplicito di core impostando la proprietà MaxCpuCount nel nodo RunConfiguration nel file runsettings.

`--TestCaseFilter|/TestCaseFilter:<Expression>`

Esegue test corrispondenti all'espressione specificata. `<Expression>` è in formato `<property>Operator<value>[|&<Expression>]`, dove Operator è `=`, `!=` o `~`. L'operatore `~` usa la semantica 'contains' ed è applicabile per le proprietà stringa come `DisplayName`. Per raggruppare le sottoespressioni vengono usate le parentesi `()`.

`-?|--Help|/?|/Help`

Stampa una breve guida per il comando.

`--logger|/logger:<Logger Uri/FriendlyName>`

Specifica un logger per i risultati dei test.

* Per pubblicare i risultati dei test in Team Foundation Server, usare il provider di logger `TfsPublisher`:

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* Per registrare i risultati in un file di risultati dei test di Visual Studio (con estensione trx), usare il provider di logger `trx`. Questa opzione crea un file nella directory dei risultati dei test con nome di file di log specificato. Se `LogFileName` non è specificato, viene creato un nome di file univoco per contenere i risultati dei test.

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

Elenca tutti i test individuati dal contenitore di test specificato.

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

ID del processo padre responsabile dell'avvio del processo corrente.

`--Port|/Port:<Port>`

Specifica la porta per la connessione socket e la ricezione dei messaggi di evento.

`--Diag|/Diag:<Path to log file>`

Abilita i log dettagliati per la piattaforma di test. I log vengono scritti nel file specificato.

`args`

Specifica argomenti aggiuntivi da passare all'adattatore. Gli argomenti sono specificati come coppie nome-valore nel formato `<n>=<v>`, dove `<n>` è il nome dell'argomento e `<v>` è il valore dell'argomento. Per separare più argomenti usare uno spazio.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--Settings|/Settings:<Settings File>`

Impostazioni da usare durante l'esecuzione di test.

`--Tests|/Tests:<Test Names>`

Esegue test con nomi corrispondenti ai valori specificati. Se si specificano più valori, separarli con virgole.

`--TestAdapterPath|/TestAdapterPath`

Durante l'esecuzione dei test, vengono usati adattatori di test personalizzati da un percorso specificato (se presenti).

`--Platform|/Platform:<Platform type>`

Architettura della piattaforma di destinazione usata per l'esecuzione dei test. I valori validi sono `x86`, `x64` e `ARM`.

`--Framework|/Framework:<Framework Version>`

Versione di .NET Framework di destinazione usata per l'esecuzione dei test. Esempi di valori validi sono `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`. Altri valori supportati sono `Framework40`, `Framework45` e `FrameworkCore10`.

`--Parallel|/Parallel`

Esegue test in parallelo. Per impostazione predefinita, tutti i core presenti nel computer sono disponibili per l'uso. Specificare un numero esplicito di core impostando la proprietà MaxCpuCount nel nodo RunConfiguration nel file runsettings.

`--TestCaseFilter|/TestCaseFilter:<Expression>`

Esegue test corrispondenti all'espressione specificata. `<Expression>` è in formato `<property>Operator<value>[|&<Expression>]`, dove Operator è `=`, `!=` o `~`. L'operatore `~` usa la semantica 'contains' ed è applicabile per le proprietà stringa come `DisplayName`. Per raggruppare le sottoespressioni vengono usate le parentesi `()`.

`-?|--Help|/?|/Help`

Stampa una breve guida per il comando.

`--logger|/logger:<Logger Uri/FriendlyName>`

Specifica un logger per i risultati dei test.

* Per pubblicare i risultati dei test in Team Foundation Server, usare il provider di logger `TfsPublisher`:

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* Per registrare i risultati in un file di risultati dei test di Visual Studio (con estensione trx), usare il provider di logger `trx`. Questa opzione crea un file nella directory dei risultati dei test con nome di file di log specificato. Se `LogFileName` non è specificato, viene creato un nome di file univoco per contenere i risultati dei test.

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

Elenca tutti i test individuati dal contenitore di test specificato.

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

ID del processo padre responsabile dell'avvio del processo corrente.

`--Port|/Port:<Port>`

Specifica la porta per la connessione socket e la ricezione dei messaggi di evento.

`--Diag|/Diag:<Path to log file>`

Abilita i log dettagliati per la piattaforma di test. I log vengono scritti nel file specificato.

`args`

Specifica argomenti aggiuntivi da passare all'adattatore. Gli argomenti sono specificati come coppie nome-valore nel formato `<n>=<v>`, dove `<n>` è il nome dell'argomento e `<v>` è il valore dell'argomento. Per separare più argomenti usare uno spazio.

---

## <a name="examples"></a>Esempi

Eseguire test in `mytestproject.dll`:

`dotnet vstest mytestproject.dll`

Eseguire test in `mytestproject.dll`, esportando in una cartella personalizzata con il nome personalizzato:

`dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path`

Eseguire test in `mytestproject.dll` e `myothertestproject.exe`:

`dotnet vstest mytestproject.dll myothertestproject.exe`

Eseguire test `TestMethod1`:

`dotnet vstest /Tests:TestMethod1`

Eseguire test `TestMethod1` e `TestMethod2`:

`dotnet vstest /Tests:TestMethod1,TestMethod2`
