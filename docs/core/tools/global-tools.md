---
title: Strumenti globali .NET Core
description: Panoramica degli strumenti globali .NET Core e dei comandi dell'interfaccia della riga di comando di .NET Core disponibili.
author: KathleenDollard
ms.date: 05/29/2018
ms.openlocfilehash: 665cee64cb92efd16f5528feb656b377f9f3283c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714163"
---
# <a name="net-core-global-tools-overview"></a>Panoramica degli strumenti globali .NET Core

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

Uno strumento globale .NET Core è uno speciale pacchetto NuGet che contiene un'applicazione console. È possibile installare uno strumento globale nel computer in un percorso predefinito incluso nella variabile di ambiente PATH o in un percorso personalizzato.

Se si vuole usare uno strumento globale .NET Core:

* Trovare le informazioni sullo strumento (in genere una pagina Web o una pagina di GitHub).
* Verificare l'autore e le statistiche nella home page per il feed (in genere NuGet.org).
* Installare lo strumento.
* Chiamare lo strumento.
* Aggiornare lo strumento.
* Disinstallare lo strumento.

> [!IMPORTANT]
> Gli strumenti globali .NET Core vengono visualizzati nel percorso ed eseguiti con attendibilità totale. Non installare gli strumenti globali .NET Core se l'autore non è attendibile.

## <a name="find-a-net-core-global-tool"></a>Trovare uno strumento globale .NET Core

Attualmente non è disponibile una funzionalità di ricerca degli strumenti globali nell'interfaccia della riga di comando di .NET Core. Di seguito sono riportati alcuni suggerimenti su come trovare gli strumenti:

* È possibile trovare gli strumenti globali .NET Core in [NuGet](https://www.nuget.org). NuGet tuttavia non consente ancora di cercare specificatamente gli strumenti globali .NET Core.
* È possibile trovare consigli sugli strumenti nei post di Blog o nel repository GitHub [natemcmaster/DotNet-Tools](https://github.com/natemcmaster/dotnet-tools) .
* È possibile visualizzare il codice sorgente per gli strumenti globali creati dal team ASP.NET nel repository GitHub [ASPNET/DotNetTools](https://github.com/aspnet/DotNetTools/) .
* Per informazioni sugli strumenti di diagnostica, vedere [strumenti globali di diagnostica DotNet di .NET Core](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).

## <a name="check-the-author-and-statistics"></a>Verificare l'autore e le statistiche

Poiché vengono eseguiti con attendibilità totale e vengono in genere installati nel percorso specificato, gli strumenti globali .NET Core possono essere molto potenti. Non scaricare gli strumenti da utenti non attendibili.

Se lo strumento è ospitato su NuGet, è possibile verificare l'autore e le statistiche eseguendo una ricerca dello strumento.

## <a name="install-a-global-tool"></a>Installare uno strumento globale

Per installare uno strumento globale, usare il comando [dotnet tool install](dotnet-tool-install.md) dell'interfaccia di comando di .NET Core. L'esempio seguente illustra come installare uno strumento globale nel percorso predefinito:

```dotnetcli
dotnet tool install -g dotnetsay
```

Se lo strumento non può essere installato, vengono visualizzati messaggi di errore. Verificare che i feed previsti vengano controllati.

Se si sta tentando di installare una versione non definitiva o una versione specifica dello strumento, è possibile specificare il numero di versione usando il formato seguente:

```dotnetcli
dotnet tool install -g <package-name> --version <version-number>
```

Se l'installazione ha esito positivo, viene visualizzato un messaggio che mostra il comando usato per chiamare lo strumento e la versione installata, simile all'esempio seguente:

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.0.0') was successfully installed.
```

Gli strumenti globali possono essere installati nella directory predefinita o in un percorso specifico. Le directory predefinite sono:

| Sistema operativo          | Percorso                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Portale di     | `%USERPROFILE%\.dotnet\tools` |

Questi percorsi vengono aggiunti al percorso dell'utente alla prima esecuzione dell'SDK in modo che gli strumenti globali installati possano essere chiamati direttamente.

Si noti che gli strumenti globali sono specifici dell'utente e non globali del computer. Per questa ragione non è possibile installare uno strumento globale disponibile per tutti gli utenti del computer. Lo strumento è disponibile solo per i singoli profili utente in cui è stato installato.

Gli strumenti globali possono anche essere installati in una directory specifica. Quando vengono installati in una directory specifica, l'utente deve verificare che il comando sia disponibile includendo la directory nel percorso, chiamando il comando con la directory specificata chiamando lo strumento dall'interno della directory specificata.
In questo caso l'interfaccia della riga di comando di .NET Core non aggiunge automaticamente il percorso alla variabile di ambiente PATH.

## <a name="use-the-tool"></a>Usare lo strumento

Dopo aver installato lo strumento, è possibile chiamarlo usando il relativo comando. Si noti che il comando potrebbe non corrispondere al nome del pacchetto.

Se il comando è `dotnetsay`, è possibile chiamarlo con:

```console
dotnetsay
```

Se l'autore dello strumento voleva che lo strumento fosse visualizzato nel contesto del prompt di `dotnet`, è possibile che lo strumento sia stato progettato in modo da essere chiamato come `dotnet <command>`, ad esempio:

```dotnetcli
dotnet doc
```

Per scoprire quali strumenti sono inclusi in un pacchetto di strumenti globali installato è possibile visualizzare l'elenco dei pacchetti installati tramite il comando [dotnet tool list](dotnet-tool-list.md).

È anche possibile cercare le istruzioni d'uso nel sito Web dello strumento o digitando uno dei comandi seguenti:

```console
<command> --help
dotnet <command> --help
```

## <a name="other-cli-commands"></a>Altri comandi dell'interfaccia della riga di comando

.NET Core SDK contiene altri comandi che supportano gli strumenti globali .NET Core. Usare uno dei comandi `dotnet tool` con una delle opzioni seguenti:

* `--global` o `-g` specifica che il comando è applicabile agli strumenti globali a livello utente.
* `--tool-path` specifica un percorso personalizzato per gli strumenti globali.

Per individuare i comandi disponibili per gli strumenti globali:

```dotnetcli
dotnet tool --help
```

L'aggiornamento di uno strumento globale prevede la disinstallazione e la reinstallazione con l'ultima versione stabile. Per aggiornare uno strumento globale, usare il comando [dotnet tool update](dotnet-tool-update.md):

```dotnetcli
dotnet tool update -g <packagename>
```

Rimuovere un strumento globale usando [dotnet tool uninstall](dotnet-tool-uninstall.md):

```dotnetcli
dotnet tool uninstall -g <packagename>
```

Per visualizzare tutti gli strumenti globali attualmente installati nel computer, con la versione e comandi, usare il comando [dotnet tool list](dotnet-tool-list.md):

```dotnetcli
dotnet tool list -g
```

## <a name="see-also"></a>Vedere anche

* [Risolvere i problemi di utilizzo degli strumenti .NET Core](troubleshoot-usage-issues.md)
