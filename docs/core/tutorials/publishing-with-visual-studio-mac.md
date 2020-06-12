---
title: Pubblicare un'applicazione console .NET Core usando Visual Studio per Mac
description: La pubblicazione crea il set di file necessari per eseguire un'applicazione .NET Core.
ms.date: 06/08/2020
ms.openlocfilehash: 67762481d3a56b8473e643f71b8df909b6e54fc6
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84713665"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio-for-mac"></a>Esercitazione: pubblicare un'applicazione console .NET Core usando Visual Studio per Mac

Questa esercitazione illustra come pubblicare un'app console in modo che gli altri utenti possano eseguirla. Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione. Per distribuire i file, copiarli nel computer di destinazione.

## <a name="prerequisites"></a>Prerequisiti

- Questa esercitazione funziona con l'app console creata in [creare un'applicazione console .NET Core in Visual Studio per Mac](with-visual-studio-mac.md).

## <a name="publish-the-app"></a>Pubblicare l'app

1. Avviare Visual Studio per Mac.

1. Aprire il progetto HelloWorld creato in [creare un'applicazione console .NET Core in Visual Studio per Mac](with-visual-studio-mac.md).

1. Verificare che Visual Studio compili la versione di rilascio dell'applicazione. Se necessario, modificare la configurazione di compilazione nella barra degli strumenti da **Debug** in **Rilascio**.

   :::image type="content" source="media/publishing-with-visual-studio-mac/toolbar-release.png" alt-text="Barra degli strumenti Visual Studio con la build di rilascio selezionata":::

1. Dal menu principale scegliere **Compila**  >  **pubblicazione nella cartella...**.

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-context-menu.png" alt-text="Menu di scelta rapida Pubblica di Visual Studio":::

1. Nella finestra **di dialogo pubblica nella cartella** selezionare **pubblica**.

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-to-folder-dialog.png" alt-text="Finestra di dialogo pubblica nella cartella di Visual Studio":::

   Verrà visualizzata la cartella publish, che mostra i file creati.

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-folder.png" alt-text="cartella di pubblicazione":::

1. Selezionare l'icona a forma di ingranaggio e selezionare **copia "pubblica" come nome percorso** dal menu di scelta rapida.

   :::image type="content" source="media/publishing-with-visual-studio-mac/copy-path.png" alt-text="Copia il percorso della cartella di pubblicazione":::

## <a name="inspect-the-files"></a>Esaminare i file

Il processo di pubblicazione crea una distribuzione dipendente dal Framework, ovvero un tipo di distribuzione in cui l'applicazione pubblicata viene eseguita in un computer in cui è installato il runtime di .NET Core. Gli utenti possono eseguire l'app pubblicata eseguendo il `dotnet HelloWorld.dll` comando da un prompt dei comandi.

Come illustrato nell'immagine precedente, l'output pubblicato include i file seguenti:

* *HelloWorld.deps.json*

  Si tratta del file delle dipendenze di runtime dell'applicazione. Definisce i componenti di .NET Core e le librerie (inclusa la libreria a collegamento dinamico che contiene l'applicazione) necessari per eseguire l'app. Per ulteriori informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

* *HelloWorld.dll*

   Si tratta della versione della [distribuzione dipendente dal Framework](../deploying/deploy-with-cli.md#framework-dependent-deployment) dell'applicazione. Per eseguire questa libreria a collegamento dinamico, immettere `dotnet HelloWorld.dll` al prompt dei comandi. Questo metodo di esecuzione dell'app funziona in qualsiasi piattaforma in cui è installato il runtime di .NET Core.

* *HelloWorld.pdb* (facoltativo per la distribuzione)

   Questo è il file di simboli di debug. Non è necessario distribuire tale file insieme all'applicazione, anche se è consigliabile salvarlo nel caso in cui sia necessario eseguire il debug della versione pubblicata dell'applicazione.

* *HelloWorld.runtimeconfig.json*

   Questo è il file di configurazione in fase di esecuzione dell'applicazione. Identifica la versione di .NET Core per la quale è stata compilata l'applicazione. È anche possibile aggiungere opzioni di configurazione. Per altre informazioni, vedere Impostazioni di configurazione della fase di [esecuzione di .NET Core](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Eseguire l'app pubblicata

1. Aprire un terminale e passare alla cartella di *pubblicazione* . A tale scopo, immettere `cd` e incollare il percorso copiato in precedenza. Ad esempio:

   ```
   cd ~/Projects/HelloWorld/HelloWorld/bin/Release/netcoreapp3.1/publish/
   ```

1. Eseguire l'app usando il `dotnet` comando:

   1. Immettere `dotnet HelloWorld.dll` e premere <kbd>invio</kbd>.

   1. Immettere un nome in risposta al prompt e premere un tasto qualsiasi per uscire.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Distribuzione di applicazioni .NET Core](../deploying/index.md)

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata pubblicata un'app console. Nell'esercitazione successiva verrà creata una libreria di classi.

> [!div class="nextstepaction"]
> [Creare una libreria di .NET Standard in Visual Studio per Mac](library-with-visual-studio-mac.md)
