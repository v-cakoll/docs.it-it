---
title: Comando dotnet vstest
description: Il comando dotnet vstest consente di compilare un progetto e tutte le relative dipendenze.
ms.date: 02/27/2020
ms.openlocfilehash: e8fa94cf12ca2fe5fb99c6e3c1dcdb52185798c0
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463291"
---
# <a name="dotnet-vstest"></a>dotnet vstest

**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet-vstest`: esegue test dai file specificati.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Blame] [--Diag <PATH_TO_LOG_FILE>]
    [--Framework <FRAMEWORK>] [--InIsolation] [-lt|--ListTests <FILE_NAME>]
    [--logger <LOGGER_URI/FRIENDLY_NAME>] [--Parallel]
    [--ParentProcessId <PROCESS_ID>] [--Platform] <PLATFORM_TYPE>
    [--Port <PORT>] [--ResultsDirectory<PATH>] [--Settings <SETTINGS_FILE>]
    [--TestAdapterPath <PATH>] [--TestCaseFilter <EXPRESSION>]
    [--Tests <TEST_NAMES>] [[--] <args>...]]

dotnet vstest -?|--Help
```

## <a name="description"></a>Descrizione

Il comando `dotnet-vstest` esegue l'applicazione della riga di comando `VSTest.Console` per eseguire unit test automatizzati.

## <a name="arguments"></a>Argomenti

- **`TEST_FILE_NAMES`**

  Eseguire i test dagli assembly specificati. Per separare più nomi di assembly di test, usare gli spazi. Sono supportati caratteri jolly.

## <a name="options"></a>Opzioni

- **`--Blame`**

  Esegue i test in modalità di segnalazione degli errori. Questa opzione è utile per isolare i test problematici che causano un arresto anomalo dell'host dei test. Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.

- **`--Diag <PATH_TO_LOG_FILE>`**

  Abilita i log dettagliati per la piattaforma di test. I log vengono scritti nel file specificato.

- **`--Framework <FRAMEWORK>`**

  Versione di .NET Framework di destinazione usata per l'esecuzione dei test. Esempi di valori validi sono `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`. Altri valori supportati sono `Framework40`, `Framework45`, `FrameworkCore10` e `FrameworkUap10`.

- **`--InIsolation`**

  Esegue i test in un processo isolato. In questo modo si riduce la probabilità di arresto del processo di *vstest.console.exe* a causa di un errore durante i test, sebbene questi ultimi potrebbero risultare più lenti.

- **`-lt|--ListTests <FILE_NAME>`**

  Elenca tutti i test individuati dal contenitore di test specificato.

- **`--logger <LOGGER_URI/FRIENDLY_NAME>`**

  Specifica un logger per i risultati di test.

  - Per pubblicare i risultati dei test in Team Foundation Server, usare il provider di logger `TfsPublisher`:

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - Per registrare i risultati in un file di risultati dei test di Visual Studio (con estensione trx), usare il provider di logger `trx`. Questa opzione crea un file nella directory dei risultati dei test con nome di file di log specificato. Se `LogFileName` non è specificato, viene creato un nome di file univoco per contenere i risultati dei test.

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`--Parallel`**

  Eseguire test in parallelo. Per impostazione predefinita, tutti i core presenti nel computer sono disponibili per l'uso. Specificare un numero esplicito `MaxCpuCount` di core `RunConfiguration` impostando la proprietà nel nodo nel file *runsettings.*

- **`--ParentProcessId <PROCESS_ID>`**

  ID del processo padre responsabile dell'avvio del processo corrente.

- **`--Platform <PLATFORM_TYPE>`**

  Architettura della piattaforma di destinazione usata per l'esecuzione dei test. I valori validi sono `x86`, `x64` e `ARM`.

- **`--Port <PORT>`**

  Specifica la porta per la connessione socket e la ricezione dei messaggi di evento.

- **`--ResultsDirectory:<PATH>`**

  Directory dei risultati dei test che verrà creata nel percorso specificato, se non esistente.

- **`--Settings <SETTINGS_FILE>`**

  Impostazioni da usare durante l'esecuzione di test.

- **`--TestAdapterPath <PATH>`**

  Durante l'esecuzione dei test, vengono usati adattatori di test personalizzati da un percorso specificato (se presenti).

- **`--TestCaseFilter <EXPRESSION>`**

  Esegue test corrispondenti all'espressione specificata. `<EXPRESSION>` è in formato `<property>Operator<value>[|&<EXPRESSION>]`, dove Operator è `=`, `!=` o `~`. L'operatore `~` usa la semantica 'contains' ed è applicabile per le proprietà stringa come `DisplayName`. Le parentesi `()` vengono utilizzate per raggruppare le sottoespressioni. Per ulteriori informazioni, vedere [Filtro TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).

- **`--Tests <TEST_NAMES>`**

  Esegue test con nomi corrispondenti ai valori specificati. Se si specificano più valori, separarli con virgole.

- **`-?|--Help`**

  Stampa una breve guida per il comando.

- **`@<file>`**

  Legge un file di risposta per altre opzioni.

- **`args`**

  Specifica argomenti aggiuntivi da passare all'adattatore. Gli argomenti sono specificati come coppie nome-valore nel formato `<n>=<v>`, dove `<n>` è il nome dell'argomento e `<v>` è il valore dell'argomento. Per separare più argomenti usare uno spazio.

## <a name="examples"></a>Esempi

Eseguire test in *mytestproject.dll*:

```dotnetcli
dotnet vstest mytestproject.dll
```

Eseguire test in *mytestproject.dll*, esportando in una cartella personalizzata con nome personalizzato:

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

Eseguire test in *mytestproject.dll* e *myothertestproject.exe*:

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

Eseguire test `TestMethod1`:

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

Eseguire test `TestMethod1` e `TestMethod2`:

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```

## <a name="see-also"></a>Vedere anche

- [Opzioni della riga di comando di VSTest.Console.exe](/visualstudio/test/vstest-console-options)
