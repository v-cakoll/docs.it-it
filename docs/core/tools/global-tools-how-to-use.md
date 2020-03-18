---
title: 'Esercitazione: Installare e usare uno strumento globale .NET CoreTutorial: Install and use a .NET Core global tool'
description: Informazioni su come installare e usare uno strumento .NET come strumento globale.
ms.date: 02/12/2020
ms.openlocfilehash: 9f8378e50fd2544eedbbaaeffb89d67800ec6880
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156738"
---
# <a name="tutorial-install-and-use-a-net-core-global-tool-using-the-net-core-cli"></a>Esercitazione: Installare e usare uno strumento globale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core global tool using the .NET Core CLI

**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive

Questo tutorial ti insegna come installare e utilizzare uno strumento globale. Si utilizza uno strumento creato nella [prima esercitazione di questa serie.](global-tools-how-to-create.md)

## <a name="prerequisites"></a>Prerequisites

* Completare la [prima esercitazione di questa serie.](global-tools-how-to-create.md)

## <a name="use-the-tool-as-a-global-tool"></a>Utilizzare lo strumento come strumento globale

1. Installare lo strumento dal pacchetto eseguendo il comando [dotnet tool install](dotnet-tool-install.md) nella cartella del progetto *microsoft.botsay:*

   ```dotnetcli
   dotnet tool install --global --add-source ./nupkg microsoft.botsay
   ```

   Il `--global` parametro indica all'interfaccia della riga di comando di .NET Core per installare i file binari dello strumento in un percorso predefinito che viene aggiunto automaticamente alla variabile di ambiente PATH.

   Il `--add-source` parametro indica all'interfaccia della riga di comando di .NET Core di utilizzare temporaneamente la directory *./nupkg* come feed di origine aggiuntivo per i pacchetti NuGet. Hai fornito al tuo pacchetto un nome univoco per assicurarti che si trovi solo nella directory *./nupkg,* non nella Nuget.org sito.

   L'output mostra il comando utilizzato per chiamare lo strumento e la versione installata:

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. Richiamare lo strumento:

   ```console
   botsay hello from the bot
   ```

   > [!NOTE]
   > Se questo comando non riesce, potrebbe essere necessario aprire un nuovo terminale per aggiornare il percorso.

1. Rimuovere lo strumento eseguendo il comando [dotnet tool uninstall:](dotnet-tool-uninstall.md)

   ```dotnetcli
   dotnet tool uninstall -g microsoft.botsay
   ```

## <a name="use-the-tool-as-a-global-tool-installed-in-a-custom-location"></a>Utilizzare lo strumento come strumento globale installato in una posizione personalizzata

1. Installare lo strumento dal pacchetto.

   In Windows:

   ```dotnetcli
   dotnet tool install --tool-path c:\dotnet-tools --add-source ./nupkg microsoft.botsay
   ```

   Su Linux o macOS:

   ```dotnetcli
   dotnet tool install --tool-path ~/bin --add-source ./nupkg microsoft.botsay
   ```

   Il `--tool-path` parametro indica all'interfaccia della riga di comando di .NET Core per installare i file binari dello strumento nel percorso specificato. Se la directory non esiste, viene creata. Questa directory non viene aggiunta automaticamente alla variabile di ambiente PATH.

   L'output mostra il comando utilizzato per chiamare lo strumento e la versione installata:

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. Richiamare lo strumento:

   In Windows:

   ```console
   c:\dotnet-tools\botsay hello from the bot
   ```

   Su Linux o macOS:

   ```console
   ~/bin/botsay hello from the bot
   ```

1. Rimuovere lo strumento eseguendo il comando [dotnet tool uninstall:](dotnet-tool-uninstall.md)

   In Windows:

   ```dotnetcli
   dotnet tool uninstall --tool-path c:\dotnet-tools microsoft.botsay
   ```

   Su Linux o macOS:

   ```dotnetcli
   dotnet tool uninstall --tool-path ~/bin microsoft.botsay
   ```

## <a name="troubleshoot"></a>Risolvere problemi

Se viene visualizzato un messaggio di errore durante l'esercitazione, vedere Risolvere i problemi di [utilizzo degli strumenti .NET Core](troubleshoot-usage-issues.md).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stato installato e usato uno strumento come strumento globale. Per installare e utilizzare lo stesso strumento di uno strumento locale, passare all'esercitazione successiva.

> [!div class="nextstepaction"]
> [Installare e utilizzare strumenti locali](local-tools-how-to-use.md)
