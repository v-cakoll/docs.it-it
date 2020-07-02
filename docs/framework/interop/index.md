---
title: Interoperabilità con codice non gestito
description: Verificare l'interoperabilità con codice non gestito. CLR si nasconde dai client e dai server in base alla differenza tra i modelli a oggetti dei componenti .NET e il codice non gestito.
ms.date: 01/17/2018
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
ms.openlocfilehash: 1cebd75907fd202715cb337593186d248107bdbb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621873"
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="cf28b-104">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="cf28b-104">Interoperating with unmanaged code</span></span>

<span data-ttu-id="cf28b-105">.NET Framework favorisce l'interazione con componenti COM, servizi COM+, librerie dei tipi esterne e molti servizi del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="cf28b-105">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="cf28b-106">I tipi di dati, le firme dei metodi e i meccanismi di gestione degli errori variano tra modelli a oggetti gestiti e non gestiti.</span><span class="sxs-lookup"><span data-stu-id="cf28b-106">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="cf28b-107">Per semplificare l'interoperabilità tra componenti .NET Framework e codice non gestito e agevolare il percorso di migrazione, Common Language Runtime nasconde ai client e ai server le differenze di questi modelli a oggetti.</span><span class="sxs-lookup"><span data-stu-id="cf28b-107">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>

<span data-ttu-id="cf28b-108">Il codice eseguito sotto il controllo del runtime viene definito codice gestito.</span><span class="sxs-lookup"><span data-stu-id="cf28b-108">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="cf28b-109">Al contrario, il codice eseguito esternamente al runtime viene definito codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="cf28b-109">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="cf28b-110">Esempi di codice non gestito sono i componenti COM, le interfacce ActiveX e le funzioni dell'API Windows.</span><span class="sxs-lookup"><span data-stu-id="cf28b-110">COM components, ActiveX interfaces, and Windows API functions are examples of unmanaged code.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="cf28b-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="cf28b-111">In this section</span></span>

[<span data-ttu-id="cf28b-112">Esposizione di componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cf28b-112">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)  
<span data-ttu-id="cf28b-113">Descrive come usare componenti COM da applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf28b-113">Describes how to use COM components from .NET Framework applications.</span></span>

[<span data-ttu-id="cf28b-114">Esposizione di componenti .NET Framework a COM</span><span class="sxs-lookup"><span data-stu-id="cf28b-114">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)  
<span data-ttu-id="cf28b-115">Descrive come usare componenti .NET Framework da applicazioni COM.</span><span class="sxs-lookup"><span data-stu-id="cf28b-115">Describes how to use .NET Framework components from COM applications.</span></span>

[<span data-ttu-id="cf28b-116">Utilizzo di funzioni di DLL non gestite</span><span class="sxs-lookup"><span data-stu-id="cf28b-116">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
<span data-ttu-id="cf28b-117">Descrive come chiamare funzioni di DLL non gestite con platform invoke.</span><span class="sxs-lookup"><span data-stu-id="cf28b-117">Describes how to call unmanaged DLL functions using platform invoke.</span></span>

[<span data-ttu-id="cf28b-118">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="cf28b-118">Interop Marshaling</span></span>](interop-marshaling.md)  
<span data-ttu-id="cf28b-119">Descrive il marshalling per l'interoperabilità COM e platform invoke.</span><span class="sxs-lookup"><span data-stu-id="cf28b-119">Describes marshaling for COM interop and platform invoke.</span></span>

[<span data-ttu-id="cf28b-120">Procedura: Eseguire il mapping di HRESULT ed eccezioni</span><span class="sxs-lookup"><span data-stu-id="cf28b-120">How to: Map HRESULTs and Exceptions</span></span>](how-to-map-hresults-and-exceptions.md)  
<span data-ttu-id="cf28b-121">Descrive il mapping tra eccezioni e valori HRESULT.</span><span class="sxs-lookup"><span data-stu-id="cf28b-121">Describes the mapping between exceptions and HRESULTs.</span></span>

[<span data-ttu-id="cf28b-122">Equivalenza del tipo e tipi di interoperabilità incorporati</span><span class="sxs-lookup"><span data-stu-id="cf28b-122">Type Equivalence and Embedded Interop Types</span></span>](type-equivalence-and-embedded-interop-types.md)  
<span data-ttu-id="cf28b-123">Descrive il modo in cui le informazioni sui tipi COM sono incorporate negli assembly e come Common Language Runtime determina l'equivalenza dei tipi COM incorporati.</span><span class="sxs-lookup"><span data-stu-id="cf28b-123">Describes how type information for COM types is embedded in assemblies, and how the common language runtime determines the equivalence of embedded COM types.</span></span>

[<span data-ttu-id="cf28b-124">Procedura: Generare assembly di interoperabilità primari tramite Tlbimp.exe</span><span class="sxs-lookup"><span data-stu-id="cf28b-124">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
<span data-ttu-id="cf28b-125">Descrive come generare assembly di interoperabilità primari usando *Tlbimp.exe* (strumento di importazione di librerie dei tipi).</span><span class="sxs-lookup"><span data-stu-id="cf28b-125">Describes how to produce primary interop assemblies using *Tlbimp.exe* (Type Library Importer).</span></span>

[<span data-ttu-id="cf28b-126">Procedura: Registrare assembly di interoperabilità primari</span><span class="sxs-lookup"><span data-stu-id="cf28b-126">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)  
<span data-ttu-id="cf28b-127">Descrive come registrare gli assembly di interoperabilità primari prima di potervi fare riferimento nei progetti.</span><span class="sxs-lookup"><span data-stu-id="cf28b-127">Describes how to register the primary interop assemblies before you can reference them in your projects.</span></span>

[<span data-ttu-id="cf28b-128">Interoperabilità COM senza registrazione</span><span class="sxs-lookup"><span data-stu-id="cf28b-128">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)  
<span data-ttu-id="cf28b-129">Descrive come l'interoperabilità COM consente di attivare componenti senza usare il Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="cf28b-129">Describes how COM interop can activate components without using the Windows registry.</span></span>

[<span data-ttu-id="cf28b-130">Procedura: Configurare i componenti COM basati su .NET Framework per l'attivazione senza registrazione</span><span class="sxs-lookup"><span data-stu-id="cf28b-130">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>](configure-net-framework-based-com-components-for-reg.md)  
<span data-ttu-id="cf28b-131">Descrive come creare un manifesto dell'applicazione e come creare e incorporare un manifesto del componente.</span><span class="sxs-lookup"><span data-stu-id="cf28b-131">Describes how to create an application manifest and how to create and embed a component manifest.</span></span>

## <a name="related-sections"></a><span data-ttu-id="cf28b-132">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="cf28b-132">Related sections</span></span>

[<span data-ttu-id="cf28b-133">Wrapper COM</span><span class="sxs-lookup"><span data-stu-id="cf28b-133">COM Wrappers</span></span>](../../standard/native-interop/com-wrappers.md)  
<span data-ttu-id="cf28b-134">Descrive i wrapper forniti dall'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="cf28b-134">Describes the wrappers provided by COM interop.</span></span>
