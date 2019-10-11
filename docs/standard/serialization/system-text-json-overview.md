---
title: Serializzare e deserializzare JSON C# con-.NET
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 5ce98a7908470a402779436db43333d46f5101fc
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180147"
---
# <a name="json-serialization-in-net---overview"></a>Serializzazione JSON in .NET-Panoramica

Lo spazio dei nomi `System.Text.Json` fornisce funzionalità per la serializzazione e la deserializzazione da JavaScript Object Notation (JSON).

La progettazione della libreria enfatizza le prestazioni elevate e l'allocazione di memoria insufficiente su un set di funzionalità esteso. Il supporto incorporato di UTF-8 ottimizza il processo di lettura e scrittura del testo JSON codificato come UTF-8, ovvero la codifica più prevalente per i dati sul Web e sui file su disco.

La libreria fornisce inoltre le classi per l'utilizzo di un modello DOM (Document Object Model) in memoria. Questa funzionalità consente l'accesso casuale in sola lettura degli elementi in una stringa o in un file JSON. 

## <a name="how-to-get-the-library"></a>Come ottenere la libreria

* La libreria è incorporata come parte del Framework condiviso di [.NET Core 3,0](https://aka.ms/netcore3download) .
* Per gli altri Framework di destinazione, installare il pacchetto NuGet [System. Text. JSON](https://www.nuget.org/packages/System.Text.Json) . Il pacchetto supporta:
  * .NET Standard 2,0 e versioni successive
  * .NET Framework 4.6.1 e versioni successive
  * .NET Core 2,0, 2,1 e 2,2

## <a name="additional-resources"></a>Risorse aggiuntive

* [Come usare la libreria](system-text-json-how-to.md)
* [Codice sorgente](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json)
* [Riferimento API](xref:System.Text.Json)
* [Guida di orientamento](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/roadmap/README.md)
* Problemi di GitHub nel repository DotNet/CoreFx
  * [Discussione sullo sviluppo di System. Text. JSON](https://github.com/dotnet/corefx/issues/33115)
  * [Tutti i problemi di System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [Problemi di System. Text. JSON con etichetta JSON-funzionalità-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc)
