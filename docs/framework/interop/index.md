---
title: "Interoperabilità con codice non gestito"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2db5b8c2425637e24086f54e8ef69b0e5aac3633
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="50307-102">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="50307-102">Interoperating with Unmanaged Code</span></span>
<span data-ttu-id="50307-103">.NET Framework favorisce l'interazione con componenti COM, servizi COM+, librerie dei tipi esterne e molti servizi del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="50307-103">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="50307-104">I tipi di dati, le firme dei metodi e i meccanismi di gestione degli errori variano tra modelli a oggetti gestiti e non gestiti.</span><span class="sxs-lookup"><span data-stu-id="50307-104">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="50307-105">Per semplificare l'interoperabilità tra componenti .NET Framework e codice non gestito e agevolare il percorso di migrazione, Common Language Runtime nasconde ai client e ai server le differenze di questi modelli a oggetti.</span><span class="sxs-lookup"><span data-stu-id="50307-105">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>  
  
 <span data-ttu-id="50307-106">Il codice eseguito sotto il controllo del runtime viene definito codice gestito.</span><span class="sxs-lookup"><span data-stu-id="50307-106">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="50307-107">Al contrario, il codice eseguito esternamente al runtime viene definito codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="50307-107">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="50307-108">Esempi di codice non gestito sono i componenti COM, le interfacce ActiveX e le funzioni dell'API Win32.</span><span class="sxs-lookup"><span data-stu-id="50307-108">COM components, ActiveX interfaces, and Win32 API functions are examples of unmanaged code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50307-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="50307-109">In This Section</span></span>  
 [<span data-ttu-id="50307-110">Argomenti sulle procedure di interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="50307-110">Interoperating with Unmanaged Code How-to Topics</span></span>](http://msdn.microsoft.com/en-us/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 <span data-ttu-id="50307-111">Fornisce i collegamenti a tutte le procedure contenute nella documentazione sui concetti relativi all'interoperabilità con codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="50307-111">Provides links to all How-to topics found in the conceptual documentation for interoperating with unmanaged code.</span></span>  
  
 [<span data-ttu-id="50307-112">Esposizione di componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="50307-112">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 <span data-ttu-id="50307-113">Descrive come usare componenti COM da applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="50307-113">Describes how to use COM components from .NET Framework applications.</span></span>  
  
 [<span data-ttu-id="50307-114">Esposizione di componenti .NET Framework a COM</span><span class="sxs-lookup"><span data-stu-id="50307-114">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="50307-115">Descrive come usare componenti .NET Framework da applicazioni COM.</span><span class="sxs-lookup"><span data-stu-id="50307-115">Describes how to use .NET Framework components from COM applications.</span></span>  
  
 [<span data-ttu-id="50307-116">Utilizzo di funzioni di DLL non gestite</span><span class="sxs-lookup"><span data-stu-id="50307-116">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="50307-117">Descrive come chiamare funzioni di DLL non gestite con platform invoke.</span><span class="sxs-lookup"><span data-stu-id="50307-117">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="50307-118">Considerazioni di progettazione per l'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="50307-118">Design Considerations for Interoperation</span></span>](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 <span data-ttu-id="50307-119">Fornisce suggerimenti per la scrittura di componenti COM integrati.</span><span class="sxs-lookup"><span data-stu-id="50307-119">Provides tips for writing integrated COM components.</span></span>  
  
 [<span data-ttu-id="50307-120">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="50307-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 <span data-ttu-id="50307-121">Descrive il marshalling per l'interoperabilità COM e platform invoke.</span><span class="sxs-lookup"><span data-stu-id="50307-121">Describes marshaling for COM interop and platform invoke.</span></span>  
  
 [<span data-ttu-id="50307-122">Procedura: Eseguire il mapping di HRESULT ed eccezioni</span><span class="sxs-lookup"><span data-stu-id="50307-122">How to: Map HRESULTs and Exceptions</span></span>](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 <span data-ttu-id="50307-123">Descrive il mapping tra eccezioni e valori HRESULT.</span><span class="sxs-lookup"><span data-stu-id="50307-123">Describes the mapping between exceptions and HRESULTs.</span></span>  
  
 [<span data-ttu-id="50307-124">Interoperabilità tramite tipi generici</span><span class="sxs-lookup"><span data-stu-id="50307-124">Interoperating Using Generic Types</span></span>](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 <span data-ttu-id="50307-125">Descrive il comportamento dei tipi generici quando vengono usati nell'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="50307-125">Describes the behavior of generic types when used in COM interop.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="50307-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="50307-126">Related Sections</span></span>  
 [<span data-ttu-id="50307-127">Interoperabilità COM avanzata</span><span class="sxs-lookup"><span data-stu-id="50307-127">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 <span data-ttu-id="50307-128">Contiene collegamenti per accedere ad altre informazioni sull'inclusione di componenti COM nell'applicazione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="50307-128">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>
