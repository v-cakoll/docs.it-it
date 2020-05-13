---
title: Serializzare e deserializzare JSON con C#-.NET
description: Questa panoramica descrive le System.Text.Json funzionalità dello spazio dei nomi per la serializzazione e la deserializzazione da JSON in .NET.
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 909d979d46b30939e304af071de65d230febd92d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380133"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>Serializzazione e deserializzazione JSON (marshalling e unmarshalling) in .NET-Panoramica

Lo `System.Text.Json` spazio dei nomi fornisce funzionalità per la serializzazione e la deserializzazione da JavaScript Object Notation (JSON).

La progettazione della libreria enfatizza le prestazioni elevate e l'allocazione di memoria insufficiente su un set di funzionalità esteso. Il supporto incorporato di UTF-8 ottimizza il processo di lettura e scrittura del testo JSON codificato come UTF-8, ovvero la codifica più prevalente per i dati sul Web e sui file su disco.

La libreria fornisce inoltre le classi per l'utilizzo di un modello DOM (Document Object Model) in memoria. Questa funzionalità consente l'accesso casuale in sola lettura degli elementi in una stringa o in un file JSON.

## <a name="how-to-get-the-library"></a>Come ottenere la libreria

* La libreria è incorporata come parte del Framework condiviso di [.NET Core 3,0](https://aka.ms/netcore3download) .
* Per altri Framework di destinazione, installare il [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) pacchetto NuGet. Il pacchetto supporta:
  * .NET Standard 2,0 e versioni successive
  * .NET Framework 4.7.2 e versioni successive
  * .NET Core 2,0, 2,1 e 2,2

## <a name="additional-resources"></a>Risorse aggiuntive

* [Come usare la libreria](system-text-json-how-to.md)
* [Come eseguire la migrazione daNewtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Come scrivere i convertitori](system-text-json-converters-how-to.md)
* [System.Text.Jsoncodice sorgente](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [System.Text.JsonRiferimento API](xref:System.Text.Json)
* [System.Text.Json. Riferimento all'API di serializzazione](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
