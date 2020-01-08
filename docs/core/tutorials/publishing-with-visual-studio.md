---
title: Pubblicare l'applicazione Hello World .NET Core con Visual Studio
description: Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione .NET Core.
author: BillWagner
ms.author: wiwagn
ms.date: 12/10/2019
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 44e799ad76848278e3731b26b14a18e7fade760f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75343170"
---
# <a name="publish-your-net-core-hello-world-application-with-visual-studio"></a>Pubblicare l'applicazione Hello World .NET Core con Visual Studio

In [creare un'applicazione Hello World con .NET Core in Visual Studio](with-visual-studio.md)è stata compilata un'applicazione console Hello World. Per [eseguire il debug dell'applicazione Hello World con Visual Studio](debugging-with-visual-studio.md), è stato testato con il debugger di Visual Studio. A questo punto è sicuro che l'applicazione funziona nel modo previsto ed è possibile pubblicarla in modo che possa essere eseguita da altri utenti. Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione. Per distribuire i file, copiarli nel computer di destinazione.

## <a name="publish-the-app"></a>Pubblicare l'app

1. Verificare che Visual Studio compili la versione di rilascio dell'applicazione. Se necessario, modificare la configurazione di compilazione nella barra degli strumenti da **Debug** in **Rilascio**.

   ![Barra degli strumenti Visual Studio con la build di rilascio selezionata](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. Fare clic con il pulsante destro del mouse sul progetto **HelloWorld**, non sulla soluzione HelloWorld, e scegliere **Pubblica** dal menu. È anche possibile selezionare **Publish HelloWorld** dal menu Main **Build** .

   ![Menu di scelta rapida Pubblica di Visual Studio](media/publishing-with-visual-studio/publish-context-menu.png)
   
1. Nella pagina selezionare **una destinazione di pubblicazione** selezionare **cartella**, quindi selezionare **Crea profilo**.

   ![Selezionare una destinazione di pubblicazione in Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)
   
1. Nella pagina **pubblica** selezionare **pubblica**.

   ![Finestra Pubblica di Visual Studio](media/publishing-with-visual-studio/publish-page.png)
   
## <a name="inspect-the-files"></a>Esaminare i file

Il processo di pubblicazione crea una distribuzione dipendente dal Framework, ovvero un tipo di distribuzione in cui l'applicazione pubblicata viene eseguita su qualsiasi piattaforma supportata da .NET Core con .NET Core installato nel sistema. Gli utenti possono eseguire l'app pubblicata facendo doppio clic sul file eseguibile o eseguendo il comando `dotnet HelloWorld.dll` da un prompt dei comandi.

Nei passaggi seguenti verranno esaminati i file creati dal processo di pubblicazione.

1. Aprire un prompt dei comandi.

   Un modo per aprire un prompt dei comandi consiste nell'immettere un **prompt dei comandi** (o in breve **cmd** ) nella casella di ricerca della barra delle applicazioni di Windows. Selezionare l'app desktop **prompt dei comandi** oppure premere **invio** se è già selezionata nei risultati della ricerca.

1. Passare all'applicazione pubblicata nella sottodirectory *bin\Release\netcoreapp3.1\publish* della directory del progetto dell'applicazione.

   ![Finestra della console con file pubblicati](media/publishing-with-visual-studio/published-files-output.png)

   Come illustrato nell'immagine, l'output pubblicato include i file seguenti:

      * *HelloWorld.deps.json*

         Si tratta del file delle dipendenze di runtime dell'applicazione. Definisce i componenti di .NET Core e le librerie (inclusa la libreria a collegamento dinamico che contiene l'applicazione) necessari per eseguire l'app. Per ulteriori informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

      * *HelloWorld.dll*

         Si tratta della versione della [distribuzione dipendente dal Framework](../deploying/deploy-with-cli.md#framework-dependent-deployment) dell'applicazione. Per eseguire questa libreria a collegamento dinamico, immettere `dotnet HelloWorld.dll` al prompt dei comandi.

      * *HelloWorld. exe*
      
         Si tratta della versione [eseguibile dipendente dal Framework](../deploying/deploy-with-cli.md#framework-dependent-executable) dell'applicazione. Per eseguirlo, immettere `HelloWorld.exe` al prompt dei comandi.

      * *HelloWorld.pdb* (facoltativo per la distribuzione)

         Questo è il file di simboli di debug. Non è necessario distribuire tale file insieme all'applicazione, anche se è consigliabile salvarlo nel caso in cui sia necessario eseguire il debug della versione pubblicata dell'applicazione.

      * *HelloWorld.runtimeconfig.json*

         Questo è il file di configurazione di runtime dell'applicazione. Identifica la versione di .NET Core per la quale è stata compilata l'applicazione. Per ulteriori informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

## <a name="additional-resources"></a>Risorse aggiuntive

- [Distribuzione di applicazioni .NET Core](../deploying/index.md)
