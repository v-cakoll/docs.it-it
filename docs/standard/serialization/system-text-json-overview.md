---
title: Serializzare e deserializzare JSON C# con-.NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 660a2831aa6a807486fc47eae880bcd11347c547
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159546"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>Serializzazione e deserializzazione JSON (marshalling e unmarshalling) in .NET-Panoramica

Lo spazio dei nomi `System.Text.Json` fornisce funzionalità per la serializzazione e la deserializzazione da JavaScript Object Notation (JSON).

La progettazione della libreria enfatizza le prestazioni elevate e l'allocazione di memoria insufficiente su un set di funzionalità esteso. Il supporto incorporato di UTF-8 ottimizza il processo di lettura e scrittura del testo JSON codificato come UTF-8, ovvero la codifica più prevalente per i dati sul Web e sui file su disco.

La libreria fornisce inoltre le classi per l'utilizzo di un modello DOM (Document Object Model) in memoria. Questa funzionalità consente l'accesso casuale in sola lettura degli elementi in una stringa o in un file JSON.

## <a name="how-to-get-the-library"></a>Come ottenere la libreria

* La libreria è incorporata come parte del Framework condiviso di [.NET Core 3,0](https://aka.ms/netcore3download) .
* Per altri Framework di destinazione, installare il pacchetto NuGet [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) . Il pacchetto supporta:
  * .NET Standard 2,0 e versioni successive
  * .NET Framework 4.7.2 e versioni successive
  * .NET Core 2,0, 2,1 e 2,2

## <a name="additional-resources"></a>Risorse aggiuntive

* [Come usare la libreria](system-text-json-how-to.md)
* [Come eseguire la migrazione da Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Come scrivere i convertitori](system-text-json-converters-how-to.md)
* [codice sorgente System.Text.Json](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [informazioni di riferimento sull'API System.Text.Json](xref:System.Text.Json)
* [System.Text.Json. Riferimento all'API di serializzazione](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
