---
title: Introduzione a C# - Acquisire familiarità con gli strumenti di sviluppo
description: Questo articolo presenta un'introduzione di base agli strumenti usati per sviluppare applicazioni C# e .NET nel computer.
ms.date: 10/23/2018
ms.openlocfilehash: fe39bd5e89bb168316b19c62d6e022e36c58fc2f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850760"
---
# <a name="become-familiar-with-the-net-development-tools"></a>Acquisire familiarità con gli strumenti di sviluppo .NET

Il primo passaggio dell'esecuzione di un'esercitazione nel computer consiste nel configurare l'ambiente di sviluppo.
L'esercitazione .NET [Hello World in 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) contiene istruzioni per la configurazione dell'ambiente di sviluppo locale in Mac, PC o Linux.

In alternativa è possibile installare [.NET Core SDK](https://dotnet.microsoft.com/download) e [Visual Studio Code](https://code.visualstudio.com/).

## <a name="basic-application-development-flow"></a>Flusso di sviluppo di applicazioni di base

Per creare le applicazioni, si userà il comando [`dotnet new`](../../../core/tools/dotnet-new.md). Questo comando genera i file e gli asset necessari per l'applicazione. Le esercitazioni introduttive su C# usano tutte il tipo di applicazione `console`. Dopo aver acquisito i concetti di base, è possibile passare a tipi di applicazione più complessi.

Gli altri comandi da usare sono [`dotnet build`](../../../core/tools/dotnet-build.md) per compilare l'eseguibile e [`dotnet run`](../../../core/tools/dotnet-run.md) per eseguire l'eseguibile.

## <a name="pick-your-tutorial"></a>Selezionare l'esercitazione

È possibile iniziare con una qualsiasi delle esercitazioni seguenti:

## <a name="numbers-in-cnumbers-in-csharp-localmd"></a>[Numeri in C#](numbers-in-csharp-local.md)

Nell'esercitazione [Numeri in C#](numbers-in-csharp-local.md) viene descritto il modo in cui i computer archiviano numeri per eseguire calcoli con tipi numerici diversi. Verranno presentati i concetti di base dell'arrotondamento e informazioni su come eseguire calcoli matematici con C#.

Questa esercitazione presuppone che sia stata già completata la lezione [Hello World](hello-world.yml).

## <a name="branches-and-loopsbranches-and-loops-localmd"></a>[Rami e cicli](branches-and-loops-local.md)

L'esercitazione [Rami e cicli](branches-and-loops-local.md) presenta i concetti di base della selezione di percorsi diversi di esecuzione del codice in base ai valori archiviati in variabili. Si apprenderanno i concetti fondamentali del flusso di controllo, ovvero i meccanismi in base ai quali i programmi prendono decisioni e scelgono azioni diverse.

Questa esercitazione presuppone che siano state già completate le lezioni [Hello World](hello-world.yml) e [Numeri in C#](numbers-in-csharp-local.md).

## <a name="list-collectionarrays-and-collectionsmd"></a>[Raccolte di elenchi](arrays-and-collections.md)

La lezione [Raccolte di elenchi](arrays-and-collections.md) offre una panoramica delle raccolte di tipo List che consentono di archiviare sequenze di dati. Si apprenderà come aggiungere e rimuovere elementi, eseguire la ricerca di elementi e ordinare gli elenchi. Verranno esaminati diversi tipi di elenchi. 

Questa esercitazione presuppone che siano state già completate le lezioni elencate sopra.

## <a name="introduction-to-classesintroduction-to-classesmd"></a>[Introduzione alle classi](introduction-to-classes.md)

L'esercitazione introduttiva finale su C# è disponibile per l'esecuzione solo nel computer, usando l'ambiente di sviluppo locale e .NET Core.
Verrà illustrato come creare un'applicazione console e verranno presentate le funzionalità orientate a oggetti di base che fanno parte del linguaggio C#.
