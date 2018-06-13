---
title: Pubblicare l'applicazione Hello World con Visual Studio 2017
description: Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione.
author: BillWagner
ms.author: wiwagn
ms.date: 10/05/2017
ms.openlocfilehash: 11421c8820dd562ba1dbb5900ba1e9bf944b45d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33212131"
---
# <a name="publish-your-hello-world-application-with-visual-studio-2017"></a>Pubblicare l'applicazione Hello World con Visual Studio 2017

In [Compilare un'applicazione Hello World usando C# con .NET Core in Visual Studio 2017](with-visual-studio.md) o [Compilare un'applicazione Hello World usando Visual Basic con .NET Core in Visual Studio 2017](vb-with-visual-studio.md) si crea un'applicazione console Hello World. In [Debug dell'applicazione Hello World usando C# con Visual Studio 2017](debugging-with-visual-studio.md) l'applicazione è stata testata con il debugger di Visual Studio. A questo punto è sicuro che l'applicazione funziona nel modo previsto ed è possibile pubblicarla in modo che possa essere eseguita da altri utenti. Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione. È possibile distribuire tali file copiandoli in un computer di destinazione.

Per pubblicare ed eseguire l'applicazione: 

1. Verificare che Visual Studio compili la versione di rilascio dell'applicazione. Se necessario, modificare la configurazione di compilazione nella barra degli strumenti da **Debug** in **Rilascio**.

   ![Barra degli strumenti di Visual Studio](media/publishing-with-visual-studio/toolbar.png)

1. Fare clic con il pulsante destro del mouse sul progetto **HelloWorld**, non sulla soluzione HelloWorld, e scegliere **Pubblica** dal menu. È anche possibile scegliere **Pubblica HelloWorld** dal menu principale **Compila** di Visual Studio.

   ![Barra degli strumenti di Visual Studio](media/publishing-with-visual-studio/publish1.png)


   ![Barra degli strumenti di Visual Studio](media/publishing-with-visual-studio/publishwindow.png)

1. Aprire una finestra della console. Ad esempio nella casella di testo **Digitare qui il testo di ricerca** nella barra delle applicazioni Windows, immettere `Command Prompt` o `cmd` per maggiore brevità e aprire una finestra della console selezionando l'applicazione desktop **Prompt dei comandi** o premendo INVIO se è selezionata nei risultati della ricerca.

1. Passare all'applicazione pubblicata nella sottodirectory `bin\release\PublishOutput` della directory del progetto dell'applicazione. Come illustrato nella figura, l'output pubblicato include i quattro file seguenti:

      * *HelloWorld.deps.json*

         File di dipendenze di runtime dell'applicazione. Definisce i componenti e le librerie di .NET Core (inclusa la libreria di collegamento dinamico che contiene l'applicazione) necessari per eseguire l'applicazione. Per altre informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime).
 
      * *HelloWorld.dll*

         File che contiene l'applicazione. È una libreria a collegamento dinamico che può essere eseguita tramite l'immissione del comando `dotnet HelloWorld.dll` in una finestra della console. 

      * *HelloWorld.pdb* (facoltativo per la distribuzione)

         File che contiene i simboli di debug. Non è necessario distribuire tale file insieme all'applicazione, anche se è consigliabile salvarlo nel caso in cui sia necessario eseguire il debug della versione pubblicata dell'applicazione.

      * *HelloWorld.runtimeconfig.json*

         File di configurazione di runtime dell'applicazione. Identifica la versione di .NET Core per la quale è stata compilata l'applicazione. Per altre informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime).  

   ![Finestra della console con file pubblicati](media/publishing-with-visual-studio/publishedfiles.png)

Il processo di pubblicazione crea una distribuzione dipendente dal framework. Si tratta di un tipo di distribuzione in cui l'applicazione pubblicata potrà essere eseguita su qualsiasi piattaforma supportata da .NET Core, se installato nel sistema. Gli utenti possono eseguire l'applicazione attivando il comando `dotnet HelloWorld.dll` da una finestra della console.

Per altre informazioni sulla pubblicazione e la distribuzione di applicazioni .NET Core, vedere [Distribuzione di applicazioni .NET Core](../../core/deploying/index.md).
