---
title: Risolvere i problemi di utilizzo degli strumenti .NET Core
description: Individuare i problemi comuni quando si eseguono gli strumenti di .NET Core e le possibili soluzioni.
author: kdollard
ms.date: 09/23/2019
ms.openlocfilehash: 45139c3441b84964b937d5d1cc63a018f8d1f0fb
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451077"
---
# <a name="troubleshoot-net-core-tool-usage-issues"></a>Risolvere i problemi di utilizzo degli strumenti .NET Core

Si potrebbero riscontrare problemi durante il tentativo di installare o eseguire uno strumento .NET Core, che può essere uno strumento globale o uno strumento locale. Questo articolo descrive le cause principali comuni e alcune possibili soluzioni.

## <a name="installed-net-core-tool-fails-to-run"></a>Non è possibile eseguire lo strumento .NET Core installato

Quando si verifica un errore di esecuzione di uno strumento .NET Core, è molto probabile che si verifichi uno dei problemi seguenti:

* Il file eseguibile per lo strumento non è stato trovato.
* La versione corretta del runtime di .NET Core non è stata trovata.

### <a name="executable-file-not-found"></a>File eseguibile non trovato

Se il file eseguibile non viene trovato, verrà visualizzato un messaggio simile al seguente:

```console
Could not execute because the specified command or file was not found.
Possible reasons for this include:
  * You misspelled a built-in dotnet command.
  * You intended to execute a .NET Core program, but dotnet-xyz does not exist.
  * You intended to run a global tool, but a dotnet-prefixed executable with this name could not be found on the PATH.
```

Il nome del file eseguibile determina il modo in cui si richiama lo strumento. La tabella seguente descrive il formato:

| Formato del nome eseguibile  | Formato chiamata   |
|-------------------------|---------------------|
| `dotnet-<toolName>.exe` | `dotnet <toolName>` |
| `<toolName>.exe`        | `<toolName>`        |

* Strumenti globali

    Gli strumenti globali possono essere installati nella directory predefinita o in una posizione specifica. Le directory predefinite sono:

    | Sistema operativo          | Percorso                          |
    |-------------|-------------------------------|
    | Linux/macOS | `$HOME/.dotnet/tools`         |
    | WINDOWS     | `%USERPROFILE%\.dotnet\tools` |

    Se si sta provando a eseguire uno strumento globale, verificare che la variabile di ambiente `PATH` nel computer contenga il percorso in cui è stato installato lo strumento globale e che il file eseguibile si trovi in tale percorso.

    L'interfaccia della riga di comando di .NET Core tenta di aggiungere i percorsi predefiniti alla variabile di ambiente PATH al primo utilizzo. Tuttavia, esistono un paio di scenari in cui il percorso potrebbe non essere aggiunto automaticamente al percorso, quindi è necessario modificare il percorso per configurarlo nei casi seguenti:

  * Se si usa Linux e si è installato il .NET Core SDK usando file con *estensione tar. gz* e non apt-get o RPM.
  * Se si usa macOS 10,15 "Catalina" o versioni successive.
  * Se si usa macOS 10,14 "Mojave" o versioni precedenti ed è stato installato il .NET Core SDK usando file con *estensione tar. gz* e non *. pkg*.
  * Se è stato installato .NET Core 3,0 SDK e la variabile di ambiente `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` è stata impostata su `false`.
  * Se è stato installato .NET Core 2,2 SDK o versioni precedenti ed è stata impostata la variabile di ambiente `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` su `true`.

  Per altre informazioni sugli strumenti globali, vedere [Cenni preliminari sugli strumenti globali di .NET Core](global-tools.md).

* Strumenti locali

  Se si sta provando a eseguire uno strumento locale, verificare che esista un file manifesto denominato *DotNet-Tools. JSON* nella directory corrente o in una delle relative directory padre. Questo file può essere contenuto anche in una cartella denominata *. config* in un punto qualsiasi della gerarchia della cartella del progetto, anziché nella cartella radice. Se *DotNet-Tools. JSON* esiste, aprirlo e verificare lo strumento che si sta tentando di eseguire. Se il file non contiene una voce per `"isRoot": true`, controllare anche ulteriormente la gerarchia dei file per ulteriori file manifesto dello strumento.

  Se si sta provando a eseguire uno strumento .NET Core installato con un percorso specificato, è necessario includere tale percorso quando si usa lo strumento. Di seguito è riportato un esempio di utilizzo di uno strumento-percorso installato:

  ```console
  ..\<toolDirectory>\dotnet-<toolName>
  ```

### <a name="runtime-not-found"></a>Runtime non trovato

Gli strumenti di .NET Core sono [applicazioni dipendenti dal Framework](../deploying/index.md#publish-runtime-dependent), ovvero si basano su un runtime di .NET Core installato nel computer. Se il runtime previsto non viene trovato, seguono le normali regole di rollforward del runtime di .NET Core, ad esempio:

* Un'applicazione esegue il roll forward alla versione di patch più recente della versione principale e secondaria specificate.
* Se non esiste un runtime corrispondente con un numero di versione principale e secondario corrispondente, viene usata la versione secondaria successiva più elevata.
* Il roll forward non viene eseguito tra due versioni di anteprima del runtime o tra versioni di anteprima e versioni di rilascio. Quindi, gli strumenti di .NET Core creati usando le versioni di anteprima devono essere ricompilati e ripubblicati dall'autore e reinstallati.

Per impostazione predefinita, il rollforward non viene eseguito in due scenari comuni:

* Sono disponibili solo versioni inferiori del runtime. Il rollforward consente solo di selezionare versioni successive del runtime.
* Sono disponibili solo versioni principali più elevate del runtime. Il rollforward non supera i limiti della versione principale.

Se un'applicazione non riesce a trovare un runtime appropriato, l'esecuzione non riesce e viene segnalato un errore.

È possibile scoprire quali runtime di .NET Core sono installati nel computer usando uno dei comandi seguenti:

```dotnetcli
dotnet --list-runtimes
dotnet --info
```

Se si ritiene che lo strumento supporti la versione di Runtime attualmente installata, è possibile contattare l'autore dello strumento e verificare se è possibile aggiornare il numero di versione o il multitarget. Dopo aver ricompilato e ripubblicato il pacchetto di strumenti in NuGet con un numero di versione aggiornato, è possibile aggiornare la copia. Sebbene ciò non accada, la soluzione più rapida per l'utente consiste nell'installare una versione del runtime che funzionerebbe con lo strumento che si sta tentando di eseguire. Per scaricare una versione specifica del runtime di .NET Core, visitare la [pagina di download di .NET Core](https://dotnet.microsoft.com/download/dotnet-core).

Se si installa il .NET Core SDK in un percorso non predefinito, è necessario impostare la variabile di ambiente `DOTNET_ROOT` alla directory che contiene il `dotnet` eseguibile.

## <a name="net-core-tool-installation-fails"></a>L'installazione dello strumento .NET Core non riesce

Esistono diversi motivi per cui l'installazione di uno strumento .NET Core globale o locale potrebbe non riuscire. Quando l'installazione dello strumento non riesce, verrà visualizzato un messaggio simile a quello riportato di seguito:

```console
Tool '{0}' failed to install. This failure may have been caused by:

* You are attempting to install a preview release and did not use the --version option to specify the version.
* A package by this name was found, but it was not a .NET Core tool.
* The required NuGet feed cannot be accessed, perhaps because of an Internet connection problem.
* You mistyped the name of the tool.

For more reasons, including package naming enforcement, visit https://aka.ms/failure-installing-tool
```

Per facilitare la diagnosi di questi errori, i messaggi NuGet vengono visualizzati direttamente all'utente, insieme al messaggio precedente. Il messaggio NuGet può essere utile per identificare il problema.

### <a name="package-naming-enforcement"></a>Imposizione dei nomi dei pacchetti

Microsoft ha modificato le linee guida sull'ID del pacchetto per gli strumenti, causando la mancata presenza di alcuni strumenti con il nome stimato. Il nuovo materiale sussidiario prevede che tutti gli strumenti Microsoft siano preceduti da "Microsoft". Questo prefisso è riservato e può essere usato solo per i pacchetti firmati con un certificato autorizzato da Microsoft.

Durante la transizione, alcuni strumenti Microsoft avranno il vecchio formato dell'ID del pacchetto, mentre altri avranno il nuovo formato:

```dotnetcli
dotnet tool install -g Microsoft.<toolName>
dotnet tool install -g <toolName>
```

Quando vengono aggiornati gli ID del pacchetto, è necessario passare al nuovo ID del pacchetto per ottenere gli aggiornamenti più recenti. I pacchetti con il nome semplificato dello strumento saranno deprecati.

### <a name="preview-releases"></a>Versioni di anteprima

* Si sta tentando di installare una versione di anteprima e non è stata usata l'opzione `--version` per specificare la versione.

Gli strumenti di .NET Core in anteprima devono essere specificati con una parte del nome per indicare che sono in anteprima. Non è necessario includere l'intera anteprima. Supponendo che i numeri di versione siano nel formato previsto, è possibile usare qualcosa di simile all'esempio seguente:

```dotnetcli
dotnet tool install -g --version 1.1.0-pre <toolName>
```

> [!NOTE]
> Il team interfaccia della riga di comando di .NET Core prevede di aggiungere un cambio di `--preview` in una versione futura per semplificare questa operazione.

### <a name="package-isnt-a-net-core-tool"></a>Il pacchetto non è uno strumento .NET Core

* Un pacchetto NuGet con questo nome è stato trovato, ma non era uno strumento .NET Core.

Se si tenta di installare un pacchetto NuGet che è un pacchetto NuGet normale e non uno strumento .NET Core, verrà visualizzato un errore simile al seguente:

> NU1212: combinazione del pacchetto di progetto non valida per `<ToolName>`. Lo stile del progetto DotnetToolReference può contenere solo riferimenti del tipo DotnetTool.

### <a name="nuget-feed-cant-be-accessed"></a>Non è possibile accedere al feed NuGet

* Non è possibile accedere al feed NuGet necessario, probabilmente a causa di un problema di connessione a Internet.

L'installazione dello strumento richiede l'accesso al feed NuGet che contiene il pacchetto di strumenti. Se il feed non è disponibile, l'operazione ha esito negativo. È possibile modificare i feed con `nuget.config`, richiedere un file di `nuget.config` specifico o specificare feed aggiuntivi con il commutatore `--add-source`. Per impostazione predefinita, NuGet genera un errore per tutti i feed che non possono connettersi. Il flag `--ignore-failed-sources` possibile ignorare queste origini non raggiungibili.

### <a name="package-id-incorrect"></a>ID pacchetto errato

* Il nome dello strumento è stato digitato in forma non consentita.

Una causa comune dell'errore è che il nome dello strumento non è corretto. Questo problema può verificarsi a causa di una digitazione errata o perché lo strumento è stato spostato o è stato deprecato. Per gli strumenti di NuGet.org, un modo per assicurarsi che il nome sia corretto è cercare lo strumento in NuGet.org e copiare il comando di installazione.

## <a name="see-also"></a>Vedere anche

* [Panoramica degli strumenti globali .NET Core](global-tools.md)
