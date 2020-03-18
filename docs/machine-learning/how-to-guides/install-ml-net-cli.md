---
title: Come installare lo strumento dell'interfaccia della riga di comando (CLI) di ML.NET
description: Informazioni su come installare, aggiornare, eseguire il downgrade e disinstallare lo strumento ML.NET command-line interface (CLI).
ms.date: 12/18/2019
ms.custom: mlnet-tooling
ms.openlocfilehash: 9f678c7117d32bf817139951db7eef2c3d0f5eb2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78848639"
---
# <a name="how-to-install-the-mlnet-command-line-interface-cli-tool"></a>Come installare lo strumento dell'interfaccia della riga di comando (CLI) di ML.NET

Scopri come installare l'interfaccia della riga di comando ML.NET (interfaccia della riga di comando) su Windows, Mac o Linux.

L'interfaccia della riga di comando ML.NET genera modelli ML.NET di buona qualità e codice sorgente usando l'apprendimento automatico automatico (AutoML) e un set di dati di training.

> [!NOTE]
> Questo argomento fa riferimento all'interfaccia della riga di comando di ML.NET e al Machine Learning automatico, attualmente in anteprima, e il materiale può essere soggetto a modifiche.

## <a name="pre-requisites"></a>Prerequisiti

- [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2)

- (Facoltativo) [Visual Studio 2017 o 2019](https://visualstudio.microsoft.com/vs/)

È possibile eseguire i progetti di codice C `F5` , `dotnet run` generati con Visual Studio premendo il tasto o con (.NET Core CLI).

Nota: se dopo l'installazione di `dotnet tool` [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) il comando non funziona, disconnettersi da Windows e accedere di nuovo.

## <a name="install"></a>Installazione

L'interfaccia della riga di comando di ML.NET viene installata come gli altri strumenti globali dotnet. Usare il comando dell'interfaccia della riga di comando di .NET Core `dotnet tool install`.

L'esempio seguente illustra come installare l'interfaccia della riga di comando di ML.NET nel percorso del feed NuGet predefinito:

```dotnetcli
dotnet tool install -g mlnet
```

Se lo strumento non può essere installato (ovvero, se non è disponibile nel feed NuGet predefinito), vengono visualizzati i messaggi di errore. Verificare che i feed previsti vengano controllati.

Se l'installazione ha esito positivo, viene visualizzato un messaggio che mostra il comando usato per chiamare lo strumento e la versione installata, simile all'esempio seguente:

```console
You can invoke the tool using the following command: mlnet
Tool 'mlnet' (version 'X.X.X') was successfully installed.
```

È possibile verificare che l'installazione sia avvenuta correttamente digitando il comando seguente:

```console
mlnet
```

Verranno visualizzate le informazioni della Guida per i comandi disponibili per lo strumento mlnet, ad esempio per il comando 'auto-train'.

## <a name="install-a-specific-release-version"></a>Installare una versione specifica

Se si sta tentando di installare una versione non definitiva o una versione specifica dello strumento, è possibile specificare il [framework](../../standard/frameworks.md) usando il formato seguente:

```dotnetcli
dotnet tool install -g mlnet --framework <FRAMEWORK>
```

È anche possibile verificare se il pacchetto è installato correttamente digitando il comando seguente:

```dotnetcli
dotnet tool list -g
```

## <a name="uninstall-the-cli-package"></a>Disinstallare il pacchetto dell'interfaccia della riga di comando

Digitare il comando seguente per disinstallare il pacchetto dal computer locale:

```dotnetcli
dotnet tool uninstall mlnet -g
```

## <a name="update-the-cli-package"></a>Aggiornare il pacchetto dell'interfaccia della riga di comando

Digitare il comando seguente per aggiornare il pacchetto del computer locale:

```dotnetcli
dotnet tool update -g mlnet
```

## <a name="set-up-cli-suggestions-tab-based-auto-completion"></a>Configurare i suggerimenti dell'interfaccia della riga di comando (completamento automatico con il tasto TAB)

Poiché è basata su `System.CommandLine`, l'interfaccia della riga di comando di ML.NET include un supporto predefinito per il completamento con il tasto TAB.

L'animazione seguente mostra un esempio del funzionamento del completamento automatico con il tasto TAB:

![image](./media/cli-tab-completion.gif)

Il completamento automatico con il tasto TAB (suggerimenti di parametri) può essere usato in *Windows PowerShell* e *bash macOS/Linux* ma non in *Windows CMD*.

Per abilitarlo nella versione di anteprima corrente è necessario che l'utente finale esegua le operazioni descritte di seguito per ogni shell. Al termine, il completamento potrà essere usato per tutte le app scritte con `System.CommandLine`, ad esempio l'interfaccia della riga di comando di ML.NET.

Nel computer in cui si vuole abilitare il completamento, è necessario eseguire due operazioni.

1. Installare lo strumento globale `dotnet-suggest` eseguendo il comando seguente:

    ```dotnetcli
    dotnet tool install dotnet-suggest -g
    ```

2. Aggiungere lo script shim appropriato al profilo della shell. Potrebbe essere necessario creare un file del profilo della shell. Lo script shim inoltra le richieste di completamento della shell allo strumento `dotnet-suggest` che delega all'app basata su `System.CommandLine` appropriata.

    - Per bash, aggiungere il contenuto di [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) a `~/.bash_profile`.

    - Per PowerShell, aggiungere il contenuto di [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) al profilo PowerShell. È possibile individuare il percorso previsto per il profilo PowerShell eseguendo il comando seguente nella console:

    ```console
    echo $profile
    ```

(Per le altre shell, [ricercare](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) o aprire un [problema](https://github.com/dotnet/System.CommandLine/issues)).

## <a name="installation-directory"></a>Directory di installazione

L'interfaccia della riga di comando di ML.NET può essere installata nella directory predefinita o in un percorso specifico. Le directory predefinite sono:

| OS          | Path                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

Questi percorsi vengono aggiunti al percorso dell'utente alla prima esecuzione dell'SDK in modo che gli strumenti globali installati possano essere chiamati direttamente.

Nota: gli strumenti globali sono specifici dell'utente e non globali del computer. Per questa ragione non è possibile installare uno strumento globale disponibile per tutti gli utenti del computer. Lo strumento è disponibile solo per i singoli profili utente in cui è stato installato.

Gli strumenti globali possono anche essere installati in una directory specifica. Quando vengono installati in una directory specifica, l'utente deve verificare che il comando sia disponibile includendo la directory nel percorso, chiamando il comando con la directory specificata chiamando lo strumento dall'interno della directory specificata.
In questo caso l'interfaccia della riga di comando di .NET Core non aggiunge automaticamente il percorso alla variabile di ambiente PATH.

## <a name="see-also"></a>Vedere anche

- [Panoramica dell'interfaccia della riga di comando ML.NET](../automate-training-with-cli.md)
- [Esercitazione: Analizzare il sentiment con l'interfaccia della riga di comando del ML.NET](../tutorials/sentiment-analysis-cli.md)
- [Guida di riferimento per i comandi di training automatico dell'interfaccia della riga di comando ML.NET](../reference/ml-net-cli-reference.md)
- [Telemetria nell'interfaccia della riga di comando ML.NET](../resources/ml-net-cli-telemetry.md)
