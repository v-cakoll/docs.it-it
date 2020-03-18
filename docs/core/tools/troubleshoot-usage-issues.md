---
title: Risolvere i problemi di utilizzo degli strumenti .NET CoreTroubleshoot .NET Core tool usage issues
description: Scopri i problemi comuni durante l'esecuzione degli strumenti .NET Core e le possibili soluzioni.
author: kdollard
ms.date: 02/14/2020
ms.openlocfilehash: ed6243f802c4d3ce56a742916a1a28676e3cd876
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146450"
---
# <a name="troubleshoot-net-core-tool-usage-issues"></a>Risolvere i problemi di utilizzo degli strumenti .NET CoreTroubleshoot .NET Core tool usage issues

Si potrebbero incontrare problemi quando si tenta di installare o eseguire uno strumento .NET Core, che può essere uno strumento globale o uno strumento locale. In questo articolo vengono descritte le cause principali comuni e alcune possibili soluzioni.

## <a name="installed-net-core-tool-fails-to-run"></a>Lo strumento .NET Core installato non viene eseguito

Quando uno strumento .NET Core non viene eseguito, molto probabilmente si è verificato uno dei seguenti problemi:

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

Il nome dell'eseguibile determina la modalità di richiamo dello strumento. Nella tabella seguente viene descritto il formato:

| Formato del nome eseguibile  | Formato di chiamata   |
|-------------------------|---------------------|
| `dotnet-<toolName>.exe` | `dotnet <toolName>` |
| `<toolName>.exe`        | `<toolName>`        |

* Strumenti globali

  Gli strumenti globali possono essere installati nella directory predefinita o in un percorso specifico. Le directory predefinite sono:

  | OS          | Path                          |
  |-------------|-------------------------------|
  | Linux/macOS | `$HOME/.dotnet/tools`         |
  | Windows     | `%USERPROFILE%\.dotnet\tools` |

  Se si sta tentando di eseguire uno `PATH` strumento globale, verificare che la variabile di ambiente nel computer contenga il percorso in cui è stato installato lo strumento globale e che l'eseguibile si trovi in tale percorso.

  L'interfaccia della riga di comando di .NET Core tenta di aggiungere il percorso predefinito alla variabile di ambiente PATH al primo utilizzo. Tuttavia, esistono alcuni scenari in cui il percorso potrebbe non essere aggiunto automaticamente a PATH:However, there are some scenarios where the location might not be added to PATH automatically:

  * Se si utilizza Linux e è stato installato .NET Core SDK utilizzando i file *.tar.gz* e non apt-get o rpm.
  * Se utilizzi macOS 10.15 "Catalina" o versioni successive.
  * Se si utilizza macOS 10.14 "Mojave" o versioni precedenti e .NET Core SDK utilizzando i file *.tar.gz* e non *.pkg*.
  * Se è stato installato .NET Core 3.0 SDK `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` e la `false`variabile di ambiente è stata impostata su .
  * Se .NET Core 2.2 SDK o versioni precedenti è stato `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` installato `true`e la variabile di ambiente è stata impostata su .

  In questi scenari o `--tool-path` se è `PATH` stata specificata l'opzione , la variabile di ambiente nel computer non contiene automaticamente il percorso in cui è stato installato lo strumento globale. In tal caso, aggiungere la posizione `$HOME/.dotnet/tools`dello `PATH` strumento (ad esempio, ) alla variabile di ambiente utilizzando il metodo fornito dalla shell per l'aggiornamento delle variabili di ambiente. Per ulteriori informazioni, vedere [Strumenti di .NET Core](global-tools.md).

* Strumenti locali

  Se si sta tentando di eseguire uno strumento locale, verificare che sia presente un file manifesto denominato *dotnet-tools.json* nella directory corrente o in una delle relative directory padre. Questo file può anche trovarsi in una cartella denominata *.config* in qualsiasi punto della gerarchia di cartelle del progetto, anziché nella cartella radice. Se *dotnet-tools.json* esiste, aprirlo e verificare la presenza dello strumento che si sta tentando di eseguire. Se il file non contiene `"isRoot": true`una voce per , controllare ulteriormente la gerarchia dei file per ulteriori file manifesto degli strumenti.

  Se si sta tentando di eseguire uno strumento .NET Core installato con un percorso specificato, è necessario includere tale percorso quando si utilizza lo strumento. Un esempio di utilizzo di uno strumento di installazione del percorso utensile è:An example of using a tool-path installed tool is:

  ```console
  ..\<toolDirectory>\dotnet-<toolName>
  ```

### <a name="runtime-not-found"></a>Runtime non trovato

Gli strumenti .NET Core sono [applicazioni dipendenti dal framework,](../deploying/index.md#publish-runtime-dependent)il che significa che si basano su un runtime .NET Core installato nel computer. Se il runtime previsto non viene trovato, seguono normali regole di rollforward del runtime .NET Core, ad esempio:If the expected runtime isn't found, they follow normal .NET Core runtime roll-forward rules such as:

* Un'applicazione esegue il roll forward alla versione di patch più recente della versione principale e secondaria specificate.
* Se non è presente alcun runtime corrispondente con un numero di versione principale e secondario corrispondente, viene utilizzata la versione secondaria successiva superiore.
* Il roll forward non viene eseguito tra due versioni di anteprima del runtime o tra versioni di anteprima e versioni di rilascio. Pertanto, gli strumenti .NET Core creati utilizzando le versioni di anteprima devono essere ricompilati e ripubblicati dall'autore e reinstallati.

Il rollforward non si verifica per impostazione predefinita in due scenari comuni:Roll-forward won't occur by default in two common scenarios:

* Sono disponibili solo versioni inferiori del runtime. Roll-forward seleziona solo le versioni successive del runtime.
* Sono disponibili solo le versioni principali superiori del runtime. Il rollforward non supera i limiti della versione principale.

Se un'applicazione non riesce a trovare un runtime appropriato, non viene eseguita e viene segnalato un errore.

È possibile scoprire quali runtime .NET Core sono installati nel computer utilizzando uno dei seguenti comandi:

```dotnetcli
dotnet --list-runtimes
dotnet --info
```

Se si ritiene che lo strumento debba supportare la versione di runtime attualmente installata, è possibile contattare l'autore dello strumento e verificare se è possibile aggiornare il numero di versione o la versione multitarget. Dopo aver ricompilato e ripubblicato il pacchetto di strumenti in NuGet con un numero di versione aggiornato, è possibile aggiornare la copia. Anche se ciò non accade, la soluzione più rapida per l'installazione di una versione del runtime che funzionerebbe con lo strumento che si sta tentando di eseguire. Per scaricare una versione specifica di .NET Core Runtime, visitare la pagina di download di [.NET Core](https://dotnet.microsoft.com/download/dotnet-core).

Se si installa .NET Core SDK in un percorso non predefinito, è necessario impostare la variabile `DOTNET_ROOT` di ambiente sulla directory che contiene l'eseguibile. `dotnet`

## <a name="net-core-tool-installation-fails"></a>Installazione dello strumento .NET Core non riuscita

L'installazione di uno strumento globale o locale .NET Core potrebbe non riuscire per diversi motivi. Quando l'installazione dello strumento non riesce, verrà visualizzato un messaggio simile al seguente:

```console
Tool '{0}' failed to install. This failure may have been caused by:

* You are attempting to install a preview release and did not use the --version option to specify the version.
* A package by this name was found, but it was not a .NET Core tool.
* The required NuGet feed cannot be accessed, perhaps because of an Internet connection problem.
* You mistyped the name of the tool.

For more reasons, including package naming enforcement, visit https://aka.ms/failure-installing-tool
```

Per diagnosticare questi errori, i messaggi NuGet vengono visualizzati direttamente all'utente, insieme al messaggio precedente. Il messaggio NuGet può aiutare a identificare il problema.

### <a name="package-naming-enforcement"></a>Applicazione della denominazione dei pacchetti

Microsoft ha modificato le linee guida sull'ID pacchetto per gli strumenti, con conseguente un numero di strumenti non vengono trovati con il nome previsto. La nuova guida è che tutti gli strumenti Microsoft sono preceduti da "Microsoft". Questo prefisso è riservato e può essere utilizzato solo per i pacchetti firmati con un certificato autorizzato Microsoft.This prefix is reserved and can only be used for packages signed with a Microsoft authorized certificate.

Durante la transizione, alcuni strumenti Microsoft avranno la vecchia forma dell'ID del pacchetto, mentre altri avranno il nuovo formato:

```dotnetcli
dotnet tool install -g Microsoft.<toolName>
dotnet tool install -g <toolName>
```

Man mano che gli ID pacchetto vengono aggiornati, è necessario passare al nuovo ID pacchetto per ottenere gli aggiornamenti più recenti. I pacchetti con il nome dello strumento semplificato saranno deprecati.

### <a name="preview-releases"></a>Anteprima delle versioni

* Si sta tentando di installare una versione di `--version` anteprima e non è stata utilizzata l'opzione per specificare la versione.

Gli strumenti .NET Core in anteprima devono essere specificati con una parte del nome per indicare che sono in anteprima. Non è necessario includere l'intera anteprima. Supponendo che i numeri di versione siano nel formato previsto, è possibile utilizzare qualcosa di simile all'esempio seguente:Assuming the version numbers are in the expected format, you can use something like the following example:

```dotnetcli
dotnet tool install -g --version 1.1.0-pre <toolName>
```

### <a name="package-isnt-a-net-core-tool"></a>Il pacchetto non è uno strumento .NET CorePackage isn't a .NET Core tool

* È stato trovato un pacchetto NuGet con questo nome, ma non è stato uno strumento .NET Core.A NuGet package by this name was found, but it wasn't a .NET Core tool.

Se si tenta di installare un pacchetto NuGet che è un normale pacchetto NuGet e non uno strumento .NET Core, verrà visualizzato un errore simile al seguente:

> NU1212: combinazione progetto-pacchetto `<ToolName>`non valida per . Lo stile di progetto DotnetToolReference può contenere solo riferimenti di tipo DotnetTool.

### <a name="nuget-feed-cant-be-accessed"></a>Impossibile accedere al feed NuGet

* Non è possibile accedere al feed NuGet richiesto, ad esempio a causa di un problema di connessione a Internet.

L'installazione dello strumento richiede l'accesso al feed NuGet che contiene il pacchetto dello strumento. Non riesce se il feed non è disponibile. È possibile modificare `nuget.config`i feed `nuget.config` con , richiedere un file `--add-source` specifico o specificare feed aggiuntivi con il commutatore. Per impostazione predefinita, NuGet genera un errore per qualsiasi feed che non può connettersi. Il `--ignore-failed-sources` flag può ignorare queste origini non raggiungibili.

### <a name="package-id-incorrect"></a>ID pacchetto non corretto

* Hai digitato male il nome dello strumento.

Un motivo di errore comune è che il nome dello strumento non è corretto. Ciò può verificarsi a causa di errori di digitazione o perché lo strumento è stato spostato o è stato deprecato. Per gli strumenti su NuGet.org, un modo per assicurarsi di avere il nome corretto consiste nel cercare lo strumento al NuGet.org e copiare il comando di installazione.

## <a name="see-also"></a>Vedere anche

* [Strumenti .NET Core](global-tools.md)
