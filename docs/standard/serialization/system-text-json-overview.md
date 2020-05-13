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
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="1be16-103">Serializzazione e deserializzazione JSON (marshalling e unmarshalling) in .NET-Panoramica</span><span class="sxs-lookup"><span data-stu-id="1be16-103">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="1be16-104">Lo `System.Text.Json` spazio dei nomi fornisce funzionalità per la serializzazione e la deserializzazione da JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="1be16-104">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="1be16-105">La progettazione della libreria enfatizza le prestazioni elevate e l'allocazione di memoria insufficiente su un set di funzionalità esteso.</span><span class="sxs-lookup"><span data-stu-id="1be16-105">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="1be16-106">Il supporto incorporato di UTF-8 ottimizza il processo di lettura e scrittura del testo JSON codificato come UTF-8, ovvero la codifica più prevalente per i dati sul Web e sui file su disco.</span><span class="sxs-lookup"><span data-stu-id="1be16-106">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="1be16-107">La libreria fornisce inoltre le classi per l'utilizzo di un modello DOM (Document Object Model) in memoria.</span><span class="sxs-lookup"><span data-stu-id="1be16-107">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="1be16-108">Questa funzionalità consente l'accesso casuale in sola lettura degli elementi in una stringa o in un file JSON.</span><span class="sxs-lookup"><span data-stu-id="1be16-108">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="1be16-109">Come ottenere la libreria</span><span class="sxs-lookup"><span data-stu-id="1be16-109">How to get the library</span></span>

* <span data-ttu-id="1be16-110">La libreria è incorporata come parte del Framework condiviso di [.NET Core 3,0](https://aka.ms/netcore3download) .</span><span class="sxs-lookup"><span data-stu-id="1be16-110">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="1be16-111">Per altri Framework di destinazione, installare il [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="1be16-111">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="1be16-112">Il pacchetto supporta:</span><span class="sxs-lookup"><span data-stu-id="1be16-112">The package supports:</span></span>
  * <span data-ttu-id="1be16-113">.NET Standard 2,0 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1be16-113">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="1be16-114">.NET Framework 4.7.2 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1be16-114">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="1be16-115">.NET Core 2,0, 2,1 e 2,2</span><span class="sxs-lookup"><span data-stu-id="1be16-115">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1be16-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1be16-116">Additional resources</span></span>

* [<span data-ttu-id="1be16-117">Come usare la libreria</span><span class="sxs-lookup"><span data-stu-id="1be16-117">How to use the library</span></span>](system-text-json-how-to.md)
* <span data-ttu-id="1be16-118">[Come eseguire la migrazione daNewtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="1be16-118">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* [<span data-ttu-id="1be16-119">Come scrivere i convertitori</span><span class="sxs-lookup"><span data-stu-id="1be16-119">How to write converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="1be16-120">[System.Text.Jsoncodice sorgente](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="1be16-120">[System.Text.Json source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span></span>
* <span data-ttu-id="1be16-121">[System.Text.JsonRiferimento API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="1be16-121">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="1be16-122">[System.Text.Json. Riferimento all'API di serializzazione](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="1be16-122">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
