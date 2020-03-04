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
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="081e2-102">Serializzazione e deserializzazione JSON (marshalling e unmarshalling) in .NET-Panoramica</span><span class="sxs-lookup"><span data-stu-id="081e2-102">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="081e2-103">Lo spazio dei nomi `System.Text.Json` fornisce funzionalità per la serializzazione e la deserializzazione da JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="081e2-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="081e2-104">La progettazione della libreria enfatizza le prestazioni elevate e l'allocazione di memoria insufficiente su un set di funzionalità esteso.</span><span class="sxs-lookup"><span data-stu-id="081e2-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="081e2-105">Il supporto incorporato di UTF-8 ottimizza il processo di lettura e scrittura del testo JSON codificato come UTF-8, ovvero la codifica più prevalente per i dati sul Web e sui file su disco.</span><span class="sxs-lookup"><span data-stu-id="081e2-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="081e2-106">La libreria fornisce inoltre le classi per l'utilizzo di un modello DOM (Document Object Model) in memoria.</span><span class="sxs-lookup"><span data-stu-id="081e2-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="081e2-107">Questa funzionalità consente l'accesso casuale in sola lettura degli elementi in una stringa o in un file JSON.</span><span class="sxs-lookup"><span data-stu-id="081e2-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="081e2-108">Come ottenere la libreria</span><span class="sxs-lookup"><span data-stu-id="081e2-108">How to get the library</span></span>

* <span data-ttu-id="081e2-109">La libreria è incorporata come parte del Framework condiviso di [.NET Core 3,0](https://aka.ms/netcore3download) .</span><span class="sxs-lookup"><span data-stu-id="081e2-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="081e2-110">Per altri Framework di destinazione, installare il pacchetto NuGet [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) .</span><span class="sxs-lookup"><span data-stu-id="081e2-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="081e2-111">Il pacchetto supporta:</span><span class="sxs-lookup"><span data-stu-id="081e2-111">The package supports:</span></span>
  * <span data-ttu-id="081e2-112">.NET Standard 2,0 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="081e2-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="081e2-113">.NET Framework 4.7.2 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="081e2-113">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="081e2-114">.NET Core 2,0, 2,1 e 2,2</span><span class="sxs-lookup"><span data-stu-id="081e2-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="081e2-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="081e2-115">Additional resources</span></span>

* [<span data-ttu-id="081e2-116">Come usare la libreria</span><span class="sxs-lookup"><span data-stu-id="081e2-116">How to use the library</span></span>](system-text-json-how-to.md)
* <span data-ttu-id="081e2-117">[Come eseguire la migrazione da Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="081e2-117">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* [<span data-ttu-id="081e2-118">Come scrivere i convertitori</span><span class="sxs-lookup"><span data-stu-id="081e2-118">How to write converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="081e2-119">[codice sorgente System.Text.Json](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="081e2-119">[System.Text.Json source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span></span>
* <span data-ttu-id="081e2-120">[informazioni di riferimento sull'API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="081e2-120">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="081e2-121">[System.Text.Json. Riferimento all'API di serializzazione](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="081e2-121">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
