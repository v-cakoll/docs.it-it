---
title: Pubblicare un'applicazione Hello World .NET Core con Visual Studio Code
description: La pubblicazione crea il set di file necessari per eseguire un'applicazione .NET Core.
ms.date: 05/28/2020
ms.openlocfilehash: b49b12bf41e3ea7be8dbc459eb7d9b1fbef25790
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84246682"
---
# <a name="tutorial-publish-a-net-core-console-application-with-visual-studio-code"></a>Esercitazione: pubblicare un'applicazione console .NET Core con Visual Studio Code

Questa esercitazione illustra come pubblicare un'app console in modo che gli altri utenti possano eseguirla. La pubblicazione crea il set di file necessari per eseguire un'applicazione. Per distribuire i file, copiarli nel computer di destinazione.

Il interfaccia della riga di comando di .NET Core viene usato per pubblicare l'app, quindi è possibile seguire questa esercitazione con un editor di codice diverso da Visual Studio Code se lo si preferisce.

## <a name="prerequisites"></a>Prerequisiti

- Questa esercitazione funziona con l'app console creata in [creare un'applicazione console .NET Core in Visual Studio Code](with-visual-studio-code.md).

## <a name="publish-the-app"></a>Pubblicare l'app

1. Aprire Visual Studio Code.

1. Aprire la cartella del progetto *HelloWorld* creata in [creare un'applicazione console .net core in Visual Studio Code](with-visual-studio-code.md).

1. Scegliere **Visualizza**  >  **terminale** dal menu principale.

   Il terminale verrà aperto nella cartella *HelloWorld* .

1. Eseguire il comando seguente:

   ```dotnetcli
   dotnet publish --configuration Release
   ```

   La configurazione di compilazione predefinita è *debug*, pertanto questo comando specifica la configurazione della build di *rilascio* . L'output della configurazione della build di rilascio ha informazioni minime sul debug simbolico ed è completamente ottimizzato.

   L'output del comando è simile a quello dell'esempio seguente:

   ```
   Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

   Determining projects to restore...
   All projects are up-to-date for restore.
   HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\HelloWorld.dll
   HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

## <a name="inspect-the-files"></a>Esaminare i file

Per impostazione predefinita, il processo di pubblicazione crea una distribuzione dipendente dal Framework, ovvero un tipo di distribuzione in cui l'applicazione pubblicata viene eseguita in un computer in cui è installato il runtime di .NET Core. Per eseguire l'app pubblicata, è possibile usare il file eseguibile o eseguire il `dotnet HelloWorld.dll` comando da un prompt dei comandi.

Nei passaggi seguenti verranno esaminati i file creati dal processo di pubblicazione.

1. Selezionare **Esplora** sulla barra di spostamento a sinistra.

1. Espandere *bin/Release/netcoreapp 3.1/Publish*.

   :::image type="content" source="media/publishing-with-visual-studio-code/published-files-output.png" alt-text="Esplora file pubblicati":::

   Come illustrato nell'immagine, l'output pubblicato include i file seguenti:

   * *HelloWorld.deps.json*

      Si tratta del file delle dipendenze di runtime dell'applicazione. Definisce i componenti di .NET Core e le librerie (inclusa la libreria a collegamento dinamico che contiene l'applicazione) necessari per eseguire l'app. Per ulteriori informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

   * *HelloWorld.dll*

      Si tratta della versione della [distribuzione dipendente dal Framework](../deploying/deploy-with-cli.md#framework-dependent-deployment) dell'applicazione. Per eseguire questa libreria a collegamento dinamico, immettere `dotnet HelloWorld.dll` al prompt dei comandi. Questo metodo di esecuzione dell'app funziona in qualsiasi piattaforma in cui è installato il runtime di .NET Core.

   * *HelloWorld. exe* (*HelloWorld* in Linux, non creato in MacOS).

      Si tratta della versione [eseguibile dipendente dal Framework](../deploying/deploy-with-cli.md#framework-dependent-executable) dell'applicazione. Il file è specifico del sistema operativo.

   * *HelloWorld.pdb* (facoltativo per la distribuzione)

      Questo è il file di simboli di debug. Non è necessario distribuire tale file insieme all'applicazione, anche se è consigliabile salvarlo nel caso in cui sia necessario eseguire il debug della versione pubblicata dell'applicazione.

   * *HelloWorld.runtimeconfig.json*

      Questo è il file di configurazione in fase di esecuzione dell'applicazione. Identifica la versione di .NET Core per la quale è stata compilata l'applicazione. È anche possibile aggiungere opzioni di configurazione. Per altre informazioni, vedere Impostazioni di configurazione della fase di [esecuzione di .NET Core](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Eseguire l'app pubblicata

1. In **Esplora risorse**fare clic con il pulsante destro del mouse sulla cartella di *pubblicazione* (oppure <kbd>premere CTRL</kbd>+ clic su MacOS) e selezionare **Apri nel terminale**.

   :::image type="content" source="media/publishing-with-visual-studio-code/open-in-terminal.png" alt-text="Menu di scelta rapida che mostra Apri nel terminale":::

1. In Windows o Linux eseguire l'app usando il file eseguibile.

   1. In Windows immettere `.\HelloWorld.exe` e premere <kbd>invio</kbd>.

   1. In Linux immettere `./HelloWorld` e premere <kbd>invio</kbd>.

   1. Immettere un nome in risposta al prompt e premere un tasto qualsiasi per uscire.

1. Eseguire l'app su qualsiasi piattaforma usando il [`dotnet`](../tools/dotnet.md) comando:

   1. Immettere `dotnet HelloWorld.dll` e premere <kbd>invio</kbd>.

   1. Immettere un nome in risposta al prompt e premere un tasto qualsiasi per uscire.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Distribuzione di applicazioni .NET Core](../deploying/index.md)

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata pubblicata un'app console. Per informazioni su come compilare le librerie, vedere [sviluppare librerie con il interfaccia della riga di comando di .NET Core](libraries.md).

<!--In the next tutorial, you create a class library.

> [!div class="nextstepaction"]
> [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md)
-->
