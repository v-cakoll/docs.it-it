---
title: Strumenti di .NET Core
description: Come installare, usare, aggiornare e rimuovere gli strumenti di .NET Core. Vengono illustrati gli strumenti globali, gli strumenti di percorso degli strumenti e gli strumenti locali.
author: KathleenDollard
ms.date: 02/12/2020
ms.openlocfilehash: d8ee30df3fe063fd41a85072d145b1b5eec7d0d0
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543391"
---
# <a name="how-to-manage-net-core-tools"></a>Come gestire gli strumenti di .NET Core

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

Uno strumento di .NET Core è un pacchetto NuGet speciale che contiene un'applicazione console. Uno strumento può essere installato nel computer nei modi seguenti:

* Come strumento globale.

  I file binari degli strumenti vengono installati in una directory predefinita aggiunta alla variabile di ambiente PATH. È possibile richiamare lo strumento da qualsiasi directory nel computer senza specificarne la posizione. Una versione di uno strumento viene utilizzata per tutte le directory nel computer.

* Come strumento globale in una posizione personalizzata, nota anche come strumento di percorso degli strumenti.

  I file binari degli strumenti vengono installati in un percorso specificato. È possibile richiamare lo strumento dalla directory di installazione o specificando la directory con il nome del comando oppure aggiungendo la directory alla variabile di ambiente PATH. Una versione di uno strumento viene utilizzata per tutte le directory nel computer.

* Come strumento locale (si applica a .NET Core SDK 3,0 e versioni successive).

  I file binari degli strumenti vengono installati in una directory predefinita. Lo strumento viene richiamato dalla directory di installazione o da una delle relative sottodirectory. Diverse directory possono utilizzare versioni diverse dello stesso strumento.
  
  L'interfaccia della riga di comando di .NET usa i file manifesto per tenere traccia degli strumenti installati come locali in una directory. Quando il file manifesto viene salvato nella directory radice di un repository di codice sorgente, un collaboratore può clonare il repository e richiamare un solo comando di interfaccia della riga di comando di .NET Core che installa tutti gli strumenti elencati nei file manifesto.

> [!IMPORTANT]
> Gli strumenti di .NET Core vengono eseguiti con attendibilità totale. Non installare uno strumento .NET Core a meno che l'autore non sia considerato attendibile.

## <a name="find-a-tool"></a>Trovare uno strumento

Attualmente .NET Core non dispone di una funzionalità di ricerca di strumenti. Ecco alcuni modi per trovare gli strumenti:

* Vedere l'elenco di strumenti nel repository GitHub [natemcmaster/DotNet-Tools](https://github.com/natemcmaster/dotnet-tools) .
* Usare [ToolGet](https://www.toolget.net/) per cercare gli strumenti .NET.
* Vedere il codice sorgente per gli strumenti creati dal team di ASP.NET Core nella [directory degli strumenti del repository GitHub DotNet/aspnetcore](https://github.com/dotnet/aspnetcore/tree/master/src/Tools).
* Informazioni sugli strumenti di diagnostica in [.NET Core DotNet Diagnostic Tools](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).
* Eseguire una ricerca nel sito Web [NuGet](https://www.nuget.org) . Tuttavia, il sito NuGet non dispone ancora di una funzionalità che consente di cercare solo i pacchetti degli strumenti.

## <a name="check-the-author-and-statistics"></a>Verificare l'autore e le statistiche

Poiché gli strumenti di .NET Core vengono eseguiti con attendibilità totale e gli strumenti globali vengono aggiunti alla variabile di ambiente PATH, possono essere molto potenti. Non scaricare gli strumenti da utenti non attendibili.

Se lo strumento è ospitato su NuGet, è possibile verificare l'autore e le statistiche eseguendo una ricerca dello strumento.

## <a name="install-a-global-tool"></a>Installare uno strumento globale

Per installare uno strumento come strumento globale, usare l'opzione `-g` o `--global` di [DotNet tool install](dotnet-tool-install.md), come illustrato nell'esempio seguente:

```dotnetcli
dotnet tool install -g dotnetsay
```

L'output Mostra il comando utilizzato per richiamare lo strumento e la versione installata, in modo analogo all'esempio seguente:

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
```

Il percorso predefinito per i file binari di uno strumento dipende dal sistema operativo:

| OS          | Path                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

Questo percorso viene aggiunto al percorso dell'utente quando viene eseguito per la prima volta l'SDK, quindi gli strumenti globali possono essere richiamati da qualsiasi directory senza specificare la posizione dello strumento.

L'accesso agli strumenti è specifico dell'utente e non del computer globale. Uno strumento globale è disponibile solo per l'utente che ha installato lo strumento.

### <a name="install-a-global-tool-in-a-custom-location"></a>Installare uno strumento globale in un percorso personalizzato

Per installare uno strumento come strumento globale in un percorso personalizzato, usare l'opzione `--tool-path` dell' [installazione dello strumento DotNet](dotnet-tool-install.md), come illustrato negli esempi seguenti.

In Windows:

```dotnetcli
dotnet tool install dotnetsay --tool-path c:\dotnet-tools
```

In Linux o macOS:

```dotnetcli
dotnet tool install dotnetsay --tool-path ~/bin
```

Il .NET Core SDK non aggiunge automaticamente questo percorso alla variabile di ambiente PATH. Per [richiamare uno strumento di percorso dello strumento](#invoke-a-tool-path-tool), è necessario assicurarsi che il comando sia disponibile usando uno dei metodi seguenti:

* Aggiungere la directory di installazione alla variabile di ambiente PATH.
* Consente di specificare il percorso completo dello strumento quando viene richiamato.
* Richiamare lo strumento dalla directory di installazione.

## <a name="install-a-local-tool"></a>Installare uno strumento locale

**Si applica a .NET Core 3,0 SDK e versioni successive.**

Per installare uno strumento solo per l'accesso locale (per la directory e le sottodirectory correnti), è necessario aggiungerlo a un file manifesto dello strumento. Per creare un file manifesto dello strumento, eseguire il comando `dotnet new tool-manifest`:

```dotnetcli
dotnet new tool-manifest
```

Questo comando crea un file manifesto denominato *DotNet-Tools. JSON* nella directory *. config* . Per aggiungere uno strumento locale al file manifesto, usare il comando [DotNet tool install](dotnet-tool-install.md) e **omettere** le opzioni `--global` e `--tool-path`, come illustrato nell'esempio seguente:

```dotnetcli
dotnet tool install dotnetsay
```

L'output del comando Mostra il file manifesto in cui si trova lo strumento appena installato, in modo simile all'esempio seguente:

```console
You can invoke the tool from this directory using the following command:
dotnet tool run dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
Entry is added to the manifest file /home/name/botsay/.config/dotnet-tools.json.
```

Nell'esempio seguente viene illustrato un file manifesto con due strumenti locali installati:

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

In genere si aggiunge uno strumento locale alla directory radice del repository. Dopo l'archiviazione del file manifesto nel repository, gli sviluppatori che estrae il codice dal repository ottengono il file manifesto più recente. Per installare tutti gli strumenti elencati nel file manifesto, eseguire il comando `dotnet tool restore`:

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

Per installare una versione non definitiva o una versione specifica di uno strumento, specificare il numero di versione usando l'opzione `--version`, come illustrato nell'esempio seguente:

```dotnetcli
dotnet tool install dotnetsay --version 2.1.3
```

## <a name="use-a-tool"></a>Usare uno strumento

Il comando utilizzato per richiamare uno strumento può essere diverso dal nome del pacchetto installato. Per visualizzare tutti gli strumenti attualmente installati nel computer per l'utente corrente, usare il comando [DotNet Tool List](dotnet-tool-list.md) :

```dotnetcli
dotnet tool list
```

L'output Mostra la versione e il comando di ogni strumento, in modo analogo all'esempio seguente:

```console
Package Id      Version      Commands       Manifest
-------------------------------------------------------------------------------------------
botsay          1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
```

Come illustrato in questo esempio, l'elenco Mostra gli strumenti locali. Per visualizzare gli strumenti globali, utilizzare l'opzione `--global` e per visualizzare gli strumenti del percorso degli strumenti, utilizzare l'opzione `--tool-path`.

### <a name="invoke-a-global-tool"></a>Richiama uno strumento globale

Per gli strumenti globali, utilizzare il comando strumento autonomamente. Se, ad esempio, il comando è `dotnetsay` o `dotnet-doc`, verrà usato per richiamare il comando:

```console
dotnetsay
dotnet-doc
```

Se il comando inizia con il prefisso `dotnet-`, un metodo alternativo per richiamare lo strumento consiste nell'usare il comando `dotnet` e omettere il prefisso del comando dello strumento. Se, ad esempio, il comando è `dotnet-doc`, il comando seguente richiama lo strumento:

```dotnetcli
dotnet doc
```

Tuttavia, nello scenario seguente non è possibile usare il comando `dotnet` per richiamare uno strumento globale:

* Uno strumento globale e uno strumento locale hanno lo stesso comando preceduto da `dotnet-`.
* Si desidera richiamare lo strumento globale da una directory che rientra nell'ambito dello strumento locale.

In questo scenario, `dotnet doc` e `dotnet dotnet-doc` richiamare lo strumento locale. Per richiamare lo strumento globale, utilizzare il comando da solo:

```dotnetcli
dotnet-doc
```

### <a name="invoke-a-tool-path-tool"></a>Richiamare uno strumento di percorso strumento

Per richiamare uno strumento globale installato usando l'opzione `tool-path`, assicurarsi che il comando sia disponibile, come illustrato [in precedenza in questo articolo](#install-a-global-tool-in-a-custom-location).

### <a name="invoke-a-local-tool"></a>Richiama uno strumento locale

Per richiamare uno strumento locale, è necessario usare il comando `dotnet` dall'interno della directory di installazione. È possibile usare il formato lungo (`dotnet tool run <COMMAND_NAME>`) o la forma breve (`dotnet <COMMAND_NAME>`), come illustrato negli esempi seguenti:

```dotnetcli
dotnet tool run dotnetsay
dotnet dotnetsay
```

Se il comando è preceduto da `dotnet-`, è possibile includere o omettere il prefisso quando si richiama lo strumento. Se, ad esempio, il comando è `dotnet-doc`, uno degli esempi seguenti richiama lo strumento locale:

```dotnetcli
dotnet tool run dotnet-doc
dotnet dotnet-doc
dotnet doc
```

## <a name="update-a-tool"></a>Aggiornare uno strumento

L'aggiornamento di uno strumento implica la disinstallazione e la reinstallazione con la versione stabile più recente. Per aggiornare uno strumento, utilizzare il comando [DotNet Tool Update](dotnet-tool-update.md) con la stessa opzione utilizzata per installare lo strumento:

```dotnetcli
dotnet tool update --global <packagename>
dotnet tool update --tool-path <packagename>
dotnet tool update <packagename>
```

Per uno strumento locale, l'SDK trova il primo file manifesto che contiene l'ID del pacchetto esaminando la directory corrente e le directory padre. Se non è presente alcun ID pacchetto in alcun file manifesto, l'SDK aggiunge una nuova voce al file manifesto più vicino.

## <a name="uninstall-a-tool"></a>Disinstallare uno strumento

Rimuovere uno strumento usando il comando [DotNet Tool uninstall](dotnet-tool-uninstall.md) con la stessa opzione usata per installare lo strumento:

```dotnetcli
dotnet tool uninstall --global <packagename>
dotnet tool uninstall --tool-path<packagename>
dotnet tool uninstall <packagename>
```

Per uno strumento locale, l'SDK trova il primo file manifesto che contiene l'ID del pacchetto esaminando la directory corrente e le directory padre.

## <a name="get-help-and-troubleshoot"></a>Ottenere assistenza e risoluzione dei problemi

Per ottenere un elenco dei comandi di `dotnet tool` disponibili, immettere il comando seguente:

```dotnetcli
dotnet tool --help
```

Per ottenere le istruzioni di utilizzo degli strumenti, immettere uno dei comandi seguenti o vedere il sito Web dello strumento:

```dotnetcli
<command> --help
dotnet <command> --help
```

Se l'installazione o l'esecuzione di uno strumento non riesce, vedere [risolvere i problemi di utilizzo degli strumenti .NET Core](troubleshoot-usage-issues.md).
