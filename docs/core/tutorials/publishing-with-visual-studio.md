---
title: Pubblicare l'applicazione Hello World con Visual Studio 2017
description: Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione.
keywords: .NET, .NET Core, applicazione console pubblicazione, distribuzione
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a19545d3-24af-4a32-9778-cfb5ae938287
ms.translationtype: HT
ms.sourcegitcommit: e0271ba3392ce8861dc916714af8c16d4581ce4f
ms.openlocfilehash: 025e132cd5b6a44e98a1270e24ba6b2f9f12812c
ms.contentlocale: it-it
ms.lasthandoff: 08/14/2017

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
      * *HelloWorld.dll*
      * *HelloWorld.pdb* (facoltativo per la distribuzione)
      * *HelloWorld.runtimeconfig.json*

   Il file *HelloWorld.pdb* contiene i simboli di debug. Non è necessario distribuire tale file insieme all'applicazione, anche se è consigliabile salvarlo nel caso in cui sia necessario eseguire il debug della versione pubblicata dell'applicazione.

   ![Finestra della console con file pubblicati](media/publishing-with-visual-studio/publishedfiles.png)

Il processo di pubblicazione crea una distribuzione dipendente dal framework. Si tratta di un tipo di distribuzione in cui l'applicazione pubblicata potrà essere eseguita su qualsiasi piattaforma supportata da .NET Core, se installato nel sistema. Gli utenti possono eseguire l'applicazione attivando il comando `dotnet HelloWorld.dll` da una finestra della console.

Per altre informazioni sulla pubblicazione e la distribuzione di applicazioni .NET Core, vedere [Distribuzione di applicazioni .NET Core](../../core/deploying/index.md).

