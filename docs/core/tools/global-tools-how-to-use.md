---
title: 'Esercitazione: installare e usare uno strumento globale di .NET Core'
description: Informazioni su come installare e usare uno strumento .NET come strumento globale.
ms.date: 02/12/2020
ms.openlocfilehash: 65047af9d8a7f2fd4c1a07f65af3a6ddbf870c5d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543873"
---
# <a name="tutorial-install-and-use-a-net-core-global-tool-using-the-net-core-cli"></a>Esercitazione: installare e usare uno strumento globale .NET Core usando il interfaccia della riga di comando di .NET Core

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

Questa esercitazione illustra come installare e usare uno strumento globale. Usare uno strumento creato nella [prima esercitazione di questa serie](global-tools-how-to-create.md).

## <a name="prerequisites"></a>Prerequisites

* Completare la [prima esercitazione di questa serie](global-tools-how-to-create.md).

## <a name="use-the-tool-as-a-global-tool"></a>Usare lo strumento come strumento globale

1. Installare lo strumento dal pacchetto eseguendo il comando [DotNet tool install](dotnet-tool-install.md) nella cartella *botsay-\<Name >* Project:

   ```dotnetcli
   dotnet tool install --global --add-source ./nupkg botsay-<name>
   ```

   Il parametro `--global` indica al interfaccia della riga di comando di .NET Core di installare i file binari dello strumento in un percorso predefinito aggiunto automaticamente alla variabile di ambiente PATH.

   Il parametro `--add-source` indica al interfaccia della riga di comando di .NET Core di usare temporaneamente la directory *./nupkg* come feed di origine aggiuntivo per i pacchetti NuGet. È stato assegnato un nome univoco al pacchetto per assicurarsi che venga trovato solo nella directory *./nupkg* , non nel sito NuGet.org. 

   L'output Mostra il comando utilizzato per chiamare lo strumento e la versione installata:

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'botsay-<name>' (version '1.0.0') was successfully installed.
   ```

1. Richiamare lo strumento:

   ```console
   botsay hello from the bot
   ```

   > [!NOTE]
   > Se questo comando non riesce, potrebbe essere necessario aprire un nuovo terminale per aggiornare il percorso.

1. Rimuovere lo strumento eseguendo il comando [DotNet Tool uninstall](dotnet-tool-uninstall.md) :

   ```dotnetcli
   dotnet tool uninstall -g botsay-<name>
   ```

## <a name="use-the-tool-as-a-global-tool-installed-in-a-custom-location"></a>Usare lo strumento come strumento globale installato in un percorso personalizzato

1. Installare lo strumento dal pacchetto.

   In Windows:

   ```dotnetcli
   dotnet tool install --tool-path c:\dotnet-tools --add-source ./nupkg botsay-<name>
   ```

   In Linux o macOS:

   ```dotnetcli
   dotnet tool install --tool-path ~/bin --add-source ./nupkg botsay-<name>
   ```

   Il parametro `--tool-path` indica al interfaccia della riga di comando di .NET Core di installare i file binari degli strumenti nel percorso specificato. Se la directory non esiste, viene creata. Questa directory non viene aggiunta automaticamente alla variabile di ambiente PATH.

   L'output Mostra il comando utilizzato per chiamare lo strumento e la versione installata:

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'botsay-<name>' (version '1.0.0') was successfully installed.
   ```

1. Richiamare lo strumento:

   In Windows:

   ```console
   c:\dotnet-tools\botsay hello from the bot
   ```

   In Linux o macOS:

   ```console
   ~/bin/botsay hello from the bot
   ```

1. Rimuovere lo strumento eseguendo il comando [DotNet Tool uninstall](dotnet-tool-uninstall.md) :

   In Windows:

   ```dotnetcli
   dotnet tool uninstall --tool-path c:\dotnet-tools botsay --add-source ./nupkg botsay-<name>
   ```

   In Linux o macOS:

   ```dotnetcli
   dotnet tool uninstall --tool-path ~/bin botsay-<name>
   ```

## <a name="troubleshoot"></a>Risolvere problemi

Se viene visualizzato un messaggio di errore mentre si segue l'esercitazione, vedere [risolvere i problemi di utilizzo degli strumenti .NET Core](troubleshoot-usage-issues.md).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stato installato e utilizzato uno strumento come strumento globale. Per installare e usare lo stesso strumento di uno strumento locale, passare all'esercitazione successiva.

> [!div class="nextstepaction"]
> [Installare e usare gli strumenti locali](local-tools-how-to-use.md)
