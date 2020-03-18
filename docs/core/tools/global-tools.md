---
title: Strumenti .NET Core
description: Come installare, utilizzare, aggiornare e rimuovere gli strumenti di .NET Core. Vengono illustrati gli strumenti globali, gli strumenti del percorso degli strumenti e gli strumenti locali.
author: KathleenDollard
ms.date: 02/12/2020
ms.openlocfilehash: 2f0101c6385c41eda49bcb2458428c1f14552617
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847787"
---
# <a name="how-to-manage-net-core-tools"></a>Come gestire gli strumenti di .NET Core

**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive

Uno strumento .NET Core è un pacchetto NuGet speciale che contiene un'applicazione console. Un utensile può essere installato sul computer nei seguenti modi:

* Come strumento globale.

  I file binari dello strumento vengono installati in una directory predefinita che viene aggiunta alla variabile di ambiente PATH. È possibile richiamare lo strumento da qualsiasi directory del computer senza specificarne la posizione. Una versione di uno strumento viene utilizzata per tutte le directory del computer.

* Come strumento globale in una posizione personalizzata (noto anche come strumento di percorso degli strumenti).

  I file binari dello strumento vengono installati in un percorso specificato. È possibile richiamare lo strumento dalla directory di installazione o fornendo alla directory il nome del comando o aggiungendo la directory alla variabile di ambiente PATH. Una versione di uno strumento viene utilizzata per tutte le directory del computer.

* Come strumento locale (si applica a .NET Core SDK 3.0 e versioni successive).

  I file binari dello strumento vengono installati in una directory predefinita. Richiamare lo strumento dalla directory di installazione o da una delle relative sottodirectory. Directory diverse possono utilizzare versioni diverse dello stesso strumento.
  
  L'interfaccia della riga di comando .NET utilizza i file manifesto per tenere traccia degli strumenti installati come locali in una directory. Quando il file manifesto viene salvato nella directory radice di un repository di codice sorgente, un collaboratore può clonare il repository e richiamare un singolo comando .NET Core CLI che installa tutti gli strumenti elencati nei file manifesto.

> [!IMPORTANT]
> Gli strumenti .NET Core vengono eseguiti con attendibilità totale. Non installare uno strumento .NET Core a meno che non si consideri attendibile l'autore.

## <a name="find-a-tool"></a>Trovare uno strumento

Attualmente, .NET Core non dispone di una funzionalità di ricerca degli strumenti. Ecco alcuni modi per trovare gli strumenti:

* Vedere l'elenco degli strumenti nel repository GitHub di [natemcmaster/dotnet-tools.](https://github.com/natemcmaster/dotnet-tools)
* Utilizzare [ToolGet](https://www.toolget.net/) per cercare gli strumenti .NET.
* Vedere il codice sorgente per gli strumenti creati dal team di ASP.NET Core nella [directory Tools del repository dotnet/aspnetcore GitHub](https://github.com/dotnet/aspnetcore/tree/master/src/Tools).
* Per informazioni sugli strumenti di diagnostica, vedere [Strumenti di diagnostica dotnet di .NET Core](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).
* Cerca nel sito Web [NuGet.](https://www.nuget.org) Tuttavia, il sito NuGet non dispone ancora di una funzionalità che consente di cercare solo i pacchetti di strumenti.

## <a name="check-the-author-and-statistics"></a>Verificare l'autore e le statistiche

Poiché gli strumenti .NET Core vengono eseguiti con attendibilità totale e gli strumenti globali vengono aggiunti alla variabile di ambiente PATH, possono essere molto potenti. Non scaricare gli strumenti da utenti non attendibili.

Se lo strumento è ospitato su NuGet, è possibile verificare l'autore e le statistiche eseguendo una ricerca dello strumento.

## <a name="install-a-global-tool"></a>Installare uno strumento globale

Per installare uno strumento come strumento `-g` `--global` globale, utilizzare l'opzione o di [installazione dello strumento dotnet](dotnet-tool-install.md), come illustrato nell'esempio seguente:

```dotnetcli
dotnet tool install -g dotnetsay
```

L'output mostra il comando utilizzato per richiamare lo strumento e la versione installata, simile all'esempio seguente:

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
```

Il percorso predefinito per i file binari di uno strumento dipende dal sistema operativo:

| OS          | Path                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

Questo percorso viene aggiunto al percorso dell'utente quando l'SDK viene eseguito per la prima volta, pertanto gli strumenti globali possono essere richiamati da qualsiasi directory senza specificare il percorso dello strumento.

L'accesso agli strumenti è specifico dell'utente, non globale del computer. Uno strumento globale è disponibile solo per l'utente che lo ha installato.

### <a name="install-a-global-tool-in-a-custom-location"></a>Installare uno strumento globale in una posizione personalizzataInstall a global tool in a custom location

Per installare uno strumento come strumento globale in `--tool-path` un percorso personalizzato, utilizzare l'opzione di installazione dello [strumento dotnet](dotnet-tool-install.md), come illustrato negli esempi seguenti.

In Windows:

```dotnetcli
dotnet tool install dotnetsay --tool-path c:\dotnet-tools
```

Su Linux o macOS:

```dotnetcli
dotnet tool install dotnetsay --tool-path ~/bin
```

.NET Core SDK non aggiunge automaticamente questo percorso alla variabile di ambiente PATH. Per [richiamare uno strumento del percorso](#invoke-a-tool-path-tool)degli strumenti, è necessario assicurarsi che il comando sia disponibile utilizzando uno dei seguenti metodi:

* Aggiungere la directory di installazione alla variabile di ambiente PATH.
* Specificare il percorso completo dello strumento quando lo si richiama.
* Richiamare lo strumento dall'interno della directory di installazione.

## <a name="install-a-local-tool"></a>Installare uno strumento locale

**Si applica a .NET Core 3.0 SDK e versioni successive.**

Per installare uno strumento solo per l'accesso locale (per la directory corrente e le sottodirectory), è necessario aggiungerlo a un file manifesto dello strumento. Per creare un file manifesto `dotnet new tool-manifest` dello strumento, eseguire il comando:

```dotnetcli
dotnet new tool-manifest
```

Questo comando crea un file manifesto denominato *dotnet-tools.json* nella directory *.config.* Per aggiungere uno strumento locale al file manifesto, utilizzare il comando `--global` `--tool-path` [dotnet tool install](dotnet-tool-install.md) e **omettere** le opzioni e , come illustrato nell'esempio seguente:

```dotnetcli
dotnet tool install dotnetsay
```

L'output del comando mostra in quale file manifesto si trova lo strumento appena installato, simile all'esempio seguente:

```console
You can invoke the tool from this directory using the following command:
dotnet tool run dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
Entry is added to the manifest file /home/name/botsay/.config/dotnet-tools.json.
```

Nell'esempio seguente viene illustrato un file manifesto con due strumenti locali installati:The following example shows a manifest file with two local tools installed:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    },
    "dotnetsay": {
      "version": "2.1.3",
      "commands": [
        "dotnetsay"
      ]
    }
  }
}
```

In genere si aggiunge uno strumento locale alla directory radice del repository. Dopo aver archiviato il file manifesto nel repository, gli sviluppatori che estraono il codice dal repository ottengono il file manifesto più recente. Per installare tutti gli strumenti elencati nel `dotnet tool restore` file manifesto, eseguire il comando:

```dotnetcli
dotnet tool restore
```

L'output indica quali strumenti sono stati ripristinati:

```console
Tool 'botsay' (version '1.0.0') was restored. Available commands: botsay
Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
Restore was successful.
```

## <a name="install-a-specific-tool-version"></a>Installare una versione specifica dello strumento

Per installare una versione non definitiva o una versione specifica di `--version` uno strumento, specificare il numero di versione utilizzando l'opzione , come illustrato nell'esempio seguente:

```dotnetcli
dotnet tool install dotnetsay --version 2.1.3
```

## <a name="use-a-tool"></a>Utilizzare uno strumento

Il comando utilizzato per richiamare uno strumento potrebbe essere diverso dal nome del pacchetto installato. Per visualizzare tutti gli strumenti attualmente installati nel computer per l'utente corrente, utilizzare il comando [dotnet tool list:](dotnet-tool-list.md)

```dotnetcli
dotnet tool list
```

L'output mostra la versione e il comando di ogni strumento, simile all'esempio seguente:The output shows each tool's version and command, similar to the following example:

```console
Package Id      Version      Commands       Manifest
-------------------------------------------------------------------------------------------
botsay          1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
```

Come illustrato in questo esempio, l'elenco mostra gli strumenti locali. Per visualizzare gli strumenti `--global` globali, utilizzare l'opzione e `--tool-path` per visualizzare gli strumenti del percorso degli strumenti, utilizzare l'opzione .

### <a name="invoke-a-global-tool"></a>Richiamare uno strumento globaleInvoke a global tool

Per gli strumenti globali, utilizzare il comando strumento da solo. Ad esempio, se `dotnetsay` il `dotnet-doc`comando è o , questo è ciò che si utilizza per richiamare il comando:

```console
dotnetsay
dotnet-doc
```

Se il comando inizia `dotnet-`con il prefisso , un `dotnet` modo alternativo per richiamare lo strumento consiste nell'utilizzare il comando e omettere il prefisso del comando dello strumento. Ad esempio, se `dotnet-doc`il comando è , il comando seguente richiama lo strumento:

```dotnetcli
dotnet doc
```

Tuttavia, nello scenario seguente non `dotnet` è possibile utilizzare il comando per richiamare uno strumento globale:However, in the following scenario you can't use the command to invoke a global tool:

* Uno strumento globale e uno locale hanno `dotnet-`lo stesso comando preceduto da .
* Si desidera richiamare lo strumento globale da una directory compresa nell'ambito dello strumento locale.

In questo `dotnet doc` scenario `dotnet dotnet-doc` e richiamare lo strumento locale. Per richiamare lo strumento globale, utilizzare il comando da solo:

```dotnetcli
dotnet-doc
```

### <a name="invoke-a-tool-path-tool"></a>Richiamare uno strumento del percorso degli strumenti

Per richiamare uno strumento globale `tool-path` installato utilizzando l'opzione , assicurarsi che il comando sia disponibile, come spiegato [in precedenza in questo articolo.](#install-a-global-tool-in-a-custom-location)

### <a name="invoke-a-local-tool"></a>Richiamare uno strumento localeInvoke a local tool

Per richiamare uno strumento locale, `dotnet` è necessario utilizzare il comando all'interno della directory di installazione. È possibile utilizzare il`dotnet tool run <COMMAND_NAME>`formato lungo (`dotnet <COMMAND_NAME>`) o il formato breve ( ), come illustrato negli esempi seguenti:

```dotnetcli
dotnet tool run dotnetsay
dotnet dotnetsay
```

Se il comando è `dotnet-`preceduto da , è possibile includere o omettere il prefisso quando si richiama lo strumento. Ad esempio, se `dotnet-doc`il comando è , uno degli esempi seguenti richiama lo strumento locale:

```dotnetcli
dotnet tool run dotnet-doc
dotnet dotnet-doc
dotnet doc
```

## <a name="update-a-tool"></a>Aggiornare uno strumento

L'aggiornamento di uno strumento comporta la disinstallazione e la reinstallazione con l'ultima versione stabile. Per aggiornare uno strumento, utilizzare il comando [dotnet tool update](dotnet-tool-update.md) con la stessa opzione utilizzata per installare lo strumento:

```dotnetcli
dotnet tool update --global <packagename>
dotnet tool update --tool-path <packagename>
dotnet tool update <packagename>
```

Per uno strumento locale, l'SDK trova il primo file manifesto che contiene l'ID del pacchetto cercando nella directory corrente e nelle directory padre. Se tale ID pacchetto non è presente in alcun file manifesto, l'SDK aggiunge una nuova voce al file manifesto più vicino.

## <a name="uninstall-a-tool"></a>Disinstallare uno strumento

Rimuovere uno strumento utilizzando il comando [dotnet tool uninstall](dotnet-tool-uninstall.md) con la stessa opzione utilizzata per installare lo strumento:

```dotnetcli
dotnet tool uninstall --global <packagename>
dotnet tool uninstall --tool-path<packagename>
dotnet tool uninstall <packagename>
```

Per uno strumento locale, l'SDK trova il primo file manifesto che contiene l'ID del pacchetto cercando nella directory corrente e nelle directory padre.

## <a name="get-help-and-troubleshoot"></a>Ottenere assistenza e risoluzione dei problemi

Per ottenere un `dotnet tool` elenco dei comandi disponibili, immettere il comando seguente:

```dotnetcli
dotnet tool --help
```

Per ottenere istruzioni sull'utilizzo dello strumento, immettere uno dei comandi seguenti o visualizzare il sito Web dello strumento:

```dotnetcli
<command> --help
dotnet <command> --help
```

Se l'installazione o l'esecuzione di uno strumento non riesce, vedere Risolvere i problemi di [utilizzo degli strumenti .NET Core](troubleshoot-usage-issues.md).

## <a name="see-also"></a>Vedere anche

- [Esercitazione: Creare uno strumento .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Create a .NET Core tool using the .NET Core CLI](global-tools-how-to-create.md)
- [Esercitazione: Installare e usare uno strumento globale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core global tool using the .NET Core CLI](global-tools-how-to-use.md)
- [Esercitazione: Installare e usare uno strumento locale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core local tool using the .NET Core CLI](local-tools-how-to-use.md)
