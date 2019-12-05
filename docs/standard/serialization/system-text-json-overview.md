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
ms.openlocfilehash: b43c3f6fd8ca56aaa99fffd40317920ee7600a2c
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802713"
---
# <a name="json-serialization-in-net---overview"></a><span data-ttu-id="1243f-102">Serializzazione JSON in .NET-Panoramica</span><span class="sxs-lookup"><span data-stu-id="1243f-102">JSON serialization in .NET - overview</span></span>

<span data-ttu-id="1243f-103">Lo spazio dei nomi `System.Text.Json` fornisce funzionalità per la serializzazione e la deserializzazione da JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="1243f-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="1243f-104">La progettazione della libreria enfatizza le prestazioni elevate e l'allocazione di memoria insufficiente su un set di funzionalità esteso.</span><span class="sxs-lookup"><span data-stu-id="1243f-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="1243f-105">Il supporto incorporato di UTF-8 ottimizza il processo di lettura e scrittura del testo JSON codificato come UTF-8, ovvero la codifica più prevalente per i dati sul Web e sui file su disco.</span><span class="sxs-lookup"><span data-stu-id="1243f-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="1243f-106">La libreria fornisce inoltre le classi per l'utilizzo di un modello DOM (Document Object Model) in memoria.</span><span class="sxs-lookup"><span data-stu-id="1243f-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="1243f-107">Questa funzionalità consente l'accesso casuale in sola lettura degli elementi in una stringa o in un file JSON.</span><span class="sxs-lookup"><span data-stu-id="1243f-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="1243f-108">Come ottenere la libreria</span><span class="sxs-lookup"><span data-stu-id="1243f-108">How to get the library</span></span>

* <span data-ttu-id="1243f-109">La libreria è incorporata come parte del Framework condiviso di [.NET Core 3,0](https://aka.ms/netcore3download) .</span><span class="sxs-lookup"><span data-stu-id="1243f-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="1243f-110">Per gli altri Framework di destinazione, installare il pacchetto NuGet [System. Text. JSON](https://www.nuget.org/packages/System.Text.Json) .</span><span class="sxs-lookup"><span data-stu-id="1243f-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="1243f-111">Il pacchetto supporta:</span><span class="sxs-lookup"><span data-stu-id="1243f-111">The package supports:</span></span>
  * <span data-ttu-id="1243f-112">.NET Standard 2,0 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1243f-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="1243f-113">.NET Framework 4.6.1 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1243f-113">.NET Framework 4.6.1 and later versions</span></span>
  * <span data-ttu-id="1243f-114">.NET Core 2,0, 2,1 e 2,2</span><span class="sxs-lookup"><span data-stu-id="1243f-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1243f-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1243f-115">Additional resources</span></span>

* [<span data-ttu-id="1243f-116">Come usare la libreria</span><span class="sxs-lookup"><span data-stu-id="1243f-116">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="1243f-117">Codice sorgente</span><span class="sxs-lookup"><span data-stu-id="1243f-117">Source code</span></span>](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Text.Json)
* [<span data-ttu-id="1243f-118">Riferimento API</span><span class="sxs-lookup"><span data-stu-id="1243f-118">API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="1243f-119">Guida di orientamento</span><span class="sxs-lookup"><span data-stu-id="1243f-119">Roadmap</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Text.Json/roadmap/README.md)
* <span data-ttu-id="1243f-120">Problemi di GitHub nel repository DotNet/CoreFx</span><span class="sxs-lookup"><span data-stu-id="1243f-120">GitHub issues in the dotnet/corefx repository</span></span>
  * [<span data-ttu-id="1243f-121">Discussione sullo sviluppo di System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="1243f-121">Discussion about the development of System.Text.Json</span></span>](https://github.com/dotnet/corefx/issues/33115) <!-- TODO: Issues are still not moved to the new repo-->
  * [<span data-ttu-id="1243f-122">Tutti i problemi di System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="1243f-122">All System.Text.Json issues</span></span>](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [<span data-ttu-id="1243f-123">Problemi di System. Text. JSON con etichetta JSON-funzionalità-doc</span><span class="sxs-lookup"><span data-stu-id="1243f-123">System.Text.Json issues labeled json-functionality-doc</span></span>](https://github.com/dotnet/runtime/labels/json-functionality-doc)
