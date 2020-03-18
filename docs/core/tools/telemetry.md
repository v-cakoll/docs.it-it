---
title: Telemetria di .NET Core SDK
description: Informazioni sulle funzionalità di telemetria degli strumenti di .NET Core SDK che raccolgono informazioni sull'utilizzo per l'analisi, i dati raccolti e il modo in cui disabilitarli.
author: KathleenDollard
ms.date: 08/27/2019
ms.openlocfilehash: 9d5d7ff09ade89712f2fbbe35224851bb1c28b4c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156686"
---
# <a name="net-core-sdk-telemetry"></a>Telemetria di .NET Core SDK

[.NET Core SDK](index.md) include una funzionalità di telemetria che raccoglie i dati di utilizzo e informazioni sulle eccezioni in caso di arresto anomalo dell'interfaccia della riga di comando di .NET Core. L'interfaccia della riga di comando di .NET Core è inclusa in .NET Core SDK ed è il set di verbi che consentono di compilare, testare e pubblicare le app .NET Core. È importante che il team di .NET sappia come vengono usati gli strumenti per consentire a Microsoft di migliorarne le funzionalità. Le informazioni sugli errori consentono al team di risolvere i problemi e correggere i bug.

I dati raccolti sono anonimi e vengono pubblicati in modo aggregato in base alla [licenza Creative Commons Attribution](https://creativecommons.org/licenses/by/4.0/).

## <a name="scope"></a>Scope

`dotnet` ha due funzioni: eseguire le app ed eseguire i comandi dell'interfaccia della riga di comando. I dati di telemetria *non vengono raccolti* quando si usa `dotnet` per avviare un'applicazione nel formato seguente:

- `dotnet [path-to-app].dll`

I dati di telemetria *vengono raccolti* quando si usano i [comandi dell’interfaccia della riga di comando di .NET Core](index.md), ad esempio:

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a>Come rifiutare esplicitamente

La funzionalità di telemetria di .NET Core SDK è abilitata per impostazione predefinita. Per rifiutare esplicitamente la funzionalità di telemetria, impostare la variabile di ambiente `DOTNET_CLI_TELEMETRY_OPTOUT` su `1` o `true`.

Una singola voce di telemetria viene inviata anche dal programma di installazione di .NET Core SDK in caso di installazione corretta. Per rifiutare esplicitamente, impostare la variabile di ambiente `DOTNET_CLI_TELEMETRY_OPTOUT` prima di installare .NET Core SDK.

## <a name="disclosure"></a>Divulgazione

La prima volta che si esegue uno dei [comandi dell'interfaccia della riga di comando di .NET Core](index.md), ad esempio `dotnet build`, .NET Core SDK visualizza un testo simile al seguente. Testo può variare leggermente a seconda della versione del SDK è in esecuzione. Questa prima esperienza riguarda la modalità di notifica della raccolta dei dati da parte di Microsoft.

```console
Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience. The data is anonymous. It is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

## <a name="data-points"></a>Punti dati

La funzionalità di telemetria non raccoglie i dati personali, ad esempio nomi utente o indirizzi di posta elettronica. Non esegue l'analisi del codice e non estrae dati a livello di progetto, ad esempio nome, repository o autore. I dati vengono inviati ai server Microsoft in modo sicuro tramite la tecnologia [Monitoraggio di Azure](https://azure.microsoft.com/services/monitor/), conservati con accesso limitato e pubblicati in base a severi controlli di sicurezza da sistemi di [archiviazione di Azure](https://azure.microsoft.com/services/storage/) sicuri.

La tutela della privacy è importante per Microsoft. Se si ritiene che la telemetria raccolga dati sensibili o che i dati siano gestiti in modo non sicuro o non appropriato, segnalare un problema nel repository [dotnet/cli](https://github.com/dotnet/cli/issues) o inviare un messaggio di posta elettronica a [dotnet@microsoft.com](mailto:dotnet@microsoft.com) per indagini più approfondite.

La funzionalità di telemetria raccoglie i dati seguenti:

| Versioni dell'SDK | Data |
|--------------|------|
| Tutti          | Timestamp della chiamata. |
| Tutti          | Comando richiamato (ad esempio, "build"), con hash a partire dalla versione 2.1. |
| Tutti          | Indirizzo IP di tre ottetti usato per determinare la posizione geografica. |
| Tutti          | Sistema operativo e versione. |
| Tutti          | ID Runtime (RID) in cui è in esecuzione l'SDK. |
| Tutti          | Versione di .NET Core SDK. |
| Tutti          | Profilo di telemetria: valore facoltativo usato solo con consenso esplicito dell'utente e usato internamente a Microsoft. |
| >= 2.0        | Argomenti e opzioni di comando: vengono raccolti vari argomenti e opzioni (non stringhe arbitrarie). Vedere [Opzioni raccolte](#collected-options). Con hash dopo la versione 2.1.300. |
| >= 2.0         | Se il SDK è in esecuzione in un contenitore. |
| >= 2.0         | Framework di destinazione (dall'evento `TargetFramework`), con hash a partire dalla versione 2.1. |
| >= 2.0         | Indirizzo MAC (Media Access Control) con hash: ID univoco e anonimo dal punto di vista crittografico (SHA256) per un computer. |
| >= 2.0         | Directory di lavoro corrente con hash. |
| >= 2.0         | Report di esito positivo dell'installazione, con nome di file EXE del programma di installazione con hash. |
| >=2.1.300     | Versione del kernel. |
| >=2.1.300     | Versione di libc. |
| >=3.0.100     | Indica se l'output è stato reindirizzato (true o false). |
| >=3.0.100     | Per un arresto anomalo dell'interfaccia della riga di comando/SDK, il tipo di eccezione e la relativa analisi dello stack (nell'analisi dello stack inviata è incluso solo il codice dell'interfaccia della riga di comando/SDK). Per altre informazioni, vedere [Dati di telemetria raccolti per le eccezioni di arresto anomalo dell'interfaccia della riga di comando o dell'SDK di .NET Core](#net-core-clisdk-crash-exception-telemetry-collected). |

### <a name="collected-options"></a>Opzioni raccolte

Alcuni comandi inviano dati aggiuntivi. Un subset di comandi invia il primo argomento:

| Comando               | Dati del primo argomento inviati                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | Guida del comando richiesta.  |
| `dotnet new <arg>`    | Nome del modello (con hash).             |
| `dotnet add <arg>`    | Parola `package` o `reference`.      |
| `dotnet remove <arg>` | Parola `package` o `reference`.      |
| `dotnet list <arg>`   | Parola `package` o `reference`.      |
| `dotnet sln <arg>`    | Parola `add`, `list` o `remove`.    |
| `dotnet nuget <arg>`  | Parola `delete`, `locals` o `push`. |

Un subset di comandi invia le opzioni selezionate se vengono usate, insieme ai relativi valori:

| Opzione                  | Comandi:                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | Tutti i comandi                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | `dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`                  |
| `--framework`           | `dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest` |
| `--runtime`             | `dotnet build`,  `dotnet publish`                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

Ad eccezione di `--verbosity` e `--sdk-package-version`, viene eseguito l'hashing di tutti gli altri valori a partire da .NET Core 2.1.100 SDK.

## <a name="net-core-clisdk-crash-exception-telemetry-collected"></a>Dati di telemetria raccolti per le eccezioni di arresto anomalo dell'interfaccia della riga di comando o dell'SDK di .NET Core

In caso di arresto anomalo dell'interfaccia della riga di comando o dell'SDK di .NET Core, vengono raccolti il nome dell'eccezione e la traccia dello stack del codice dell'interfaccia della riga di comando o dell'SDK. Queste informazioni vengono raccolte per valutare i problemi e migliorare la qualità di .NET Core SDK e dell'interfaccia della riga di comando di .NET Core. Questo articolo include informazioni sui dati raccolti da Microsoft. Sono anche disponibili suggerimenti su come gli utenti che creano la propria versione di .NET Core SDK possono evitare la divulgazione accidentale di informazioni personali o sensibili.

### <a name="types-of-collected-data"></a>Tipi di dati raccolti

L'interfaccia della riga di comando di .NET Core raccoglie informazioni solo per l'interfaccia della riga di comando o l'SDK e non per le eccezioni nell'applicazione. I dati raccolti contengono il nome dell'eccezione e l'analisi dello stack. L'analisi dello stack riguarda il codice dell'interfaccia della riga di comando o dell'SDK.

L'esempio seguente mostra il tipo di dati raccolti:

```console
System.IO.IOException
at System.ConsolePal.WindowsConsoleStream.Write(Byte[] buffer, Int32 offset, Int32 count)
at System.IO.StreamWriter.Flush(Boolean flushStream, Boolean flushEncoder)
at System.IO.StreamWriter.Write(Char[] buffer)
at System.IO.TextWriter.WriteLine()
at System.IO.TextWriter.SyncTextWriter.WriteLine()
at Microsoft.DotNet.Cli.Utils.Reporter.WriteLine()
at Microsoft.DotNet.Tools.Run.RunCommand.EnsureProjectIsBuilt()
at Microsoft.DotNet.Tools.Run.RunCommand.Execute()
at Microsoft.DotNet.Tools.Run.RunCommand.Run(String[] args)
at Microsoft.DotNet.Cli.Program.ProcessArgs(String[] args, ITelemetry telemetryClient)
at Microsoft.DotNet.Cli.Program.Main(String[] args)
```

### <a name="avoid-inadvertent-disclosure-of-information"></a>Evitare la divulgazione involontaria di informazioni

I collaboratori di .NET Core e chiunque esegua una versione personalizzata di .NET Core SDK devono tenere conto del percorso del codice sorgente dell'SDK. Se si verifica un arresto anomalo durante l'uso di un'istanza di .NET Core SDK che rappresenta una compilazione di debug personalizzata o è configurata con file di simboli di compilazione personalizzati, il percorso del file di origine dell'SDK dal computer di compilazione viene raccolto come parte dell'analisi dello stack e non viene sottoposto ad hashing.

Per questo motivo, le compilazioni personalizzate di .NET Core SDK non devono trovarsi in directory i cui nomi di percorso espongono informazioni personali o sensibili.

## <a name="see-also"></a>Vedere anche

- [.NET Core CLI Telemetry - 2019 Q2 Data](https://dotnet.microsoft.com/platform/telemetry/dotnet-core-cli-2019q2) (Telemetria dell'interfaccia della riga di comando di .NET Core - Dati T2 2019)
- [Telemetry reference source (dotnet/cli repository)](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry) (Origine riferimento di telemetria - repository dotnet/cli)
