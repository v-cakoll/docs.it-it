---
title: Pubblicare l'applicazione Hello World .NET Core con Visual Studio
description: Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione .NET Core.
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 745fb2af332afa278c78ec9baeea7230fe725c02
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241494"
---
# <a name="tutorial-publish-a-net-core-console-application-with-visual-studio"></a>Esercitazione: pubblicare un'applicazione console .NET Core con Visual Studio

Questa esercitazione illustra come pubblicare un'app console in modo che gli altri utenti possano eseguirla. Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione. Per distribuire i file, copiarli nel computer di destinazione.

## <a name="prerequisites"></a>Prerequisiti

- Questa esercitazione funziona con l'app console creata in [creare un'applicazione console .NET Core in Visual Studio 2019](with-visual-studio.md).

## <a name="publish-the-app"></a>Pubblicare l'app

1. Verificare che Visual Studio compili la versione di rilascio dell'applicazione. Se necessario, modificare la configurazione di compilazione nella barra degli strumenti da **Debug** in **Rilascio**.

   ![Barra degli strumenti Visual Studio con la build di rilascio selezionata](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. Fare clic con il pulsante destro del mouse sul progetto **HelloWorld** (non sulla soluzione HelloWorld) e scegliere **pubblica** dal menu.

   ![Menu di scelta rapida Pubblica di Visual Studio](media/publishing-with-visual-studio/publish-context-menu.png)

1. Nella scheda **destinazione** della pagina **pubblica** Selezionare **cartella**, quindi fare clic su **Avanti**.

   ![Selezionare una destinazione di pubblicazione in Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)

1. Nella scheda **percorso** della pagina **pubblica** Selezionare **fine**.

   ![Scheda percorso pagina di pubblicazione di Visual Studio](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. Nella scheda **pubblica** della finestra **pubblica** Selezionare **pubblica**.

   ![Finestra Pubblica di Visual Studio](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a>Esaminare i file

Il processo di pubblicazione crea una distribuzione dipendente dal Framework, ovvero un tipo di distribuzione in cui l'applicazione pubblicata viene eseguita nel computer in cui è installato il runtime di .NET Core. Gli utenti possono eseguire l'app pubblicata facendo doppio clic sul file eseguibile o eseguendo il `dotnet HelloWorld.dll` comando da un prompt dei comandi.

Nei passaggi seguenti verranno esaminati i file creati dal processo di pubblicazione.

1. In **Esplora soluzioni**selezionare **Mostra tutti i file**.

1. Nella cartella del progetto espandere *bin/Release/netcoreapp 3.1/Publish*.

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Esplora soluzioni la visualizzazione dei file pubblicati":::

   Come illustrato nell'immagine, l'output pubblicato include i file seguenti:

   * *HelloWorld.deps.json*

      Si tratta del file delle dipendenze di runtime dell'applicazione. Definisce i componenti di .NET Core e le librerie (inclusa la libreria a collegamento dinamico che contiene l'applicazione) necessari per eseguire l'app. Per ulteriori informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

   * *HelloWorld.dll*

      Si tratta della versione della [distribuzione dipendente dal Framework](../deploying/deploy-with-cli.md#framework-dependent-deployment) dell'applicazione. Per eseguire questa libreria a collegamento dinamico, immettere `dotnet HelloWorld.dll` al prompt dei comandi. Questo metodo di esecuzione dell'app funziona in qualsiasi piattaforma in cui è installato il runtime di .NET Core.

   * *HelloWorld. exe*

      Si tratta della versione [eseguibile dipendente dal Framework](../deploying/deploy-with-cli.md#framework-dependent-executable) dell'applicazione. Per eseguirlo, immettere `HelloWorld.exe` al prompt dei comandi. Il file è specifico del sistema operativo.

   * *HelloWorld.pdb* (facoltativo per la distribuzione)

      Questo è il file di simboli di debug. Non è necessario distribuire tale file insieme all'applicazione, anche se è consigliabile salvarlo nel caso in cui sia necessario eseguire il debug della versione pubblicata dell'applicazione.

   * *HelloWorld.runtimeconfig.json*

      Questo è il file di configurazione in fase di esecuzione dell'applicazione. Identifica la versione di .NET Core per la quale è stata compilata l'applicazione. È anche possibile aggiungere opzioni di configurazione. Per altre informazioni, vedere Impostazioni di configurazione della fase di [esecuzione di .NET Core](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Eseguire l'app pubblicata

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sulla cartella *Publish* e scegliere **Copia percorso completo**.

1. Aprire un prompt dei comandi e passare alla cartella di *pubblicazione* . Immettere `cd` e incollare il percorso completo. Ad esempio:

   ```
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. Eseguire l'app usando il file eseguibile:

   1. Immettere `HelloWorld.exe` e premere <kbd>invio</kbd>.

   1. Immettere un nome in risposta al prompt e premere un tasto qualsiasi per uscire.

1. Eseguire l'app usando il `dotnet` comando:

   1. Immettere `dotnet HelloWorld.dll` e premere <kbd>invio</kbd>.

   1. Immettere un nome in risposta al prompt e premere un tasto qualsiasi per uscire.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Distribuzione di applicazioni .NET Core](../deploying/index.md)

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata pubblicata un'app console. Nell'esercitazione successiva verrà creata una libreria di classi.

> [!div class="nextstepaction"]
> [Creare una libreria .NET Standard in Visual Studio](library-with-visual-studio.md)
