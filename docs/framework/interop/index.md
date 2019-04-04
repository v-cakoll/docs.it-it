---
title: Interoperabilità con codice non gestito
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: edec95ea729fdf26e384b6658c241ca307e60851
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58408977"
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="3a45d-102">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="3a45d-102">Interoperating with unmanaged code</span></span>

<span data-ttu-id="3a45d-103">.NET Framework favorisce l'interazione con componenti COM, servizi COM+, librerie dei tipi esterne e molti servizi del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3a45d-103">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="3a45d-104">I tipi di dati, le firme dei metodi e i meccanismi di gestione degli errori variano tra modelli a oggetti gestiti e non gestiti.</span><span class="sxs-lookup"><span data-stu-id="3a45d-104">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="3a45d-105">Per semplificare l'interoperabilità tra componenti .NET Framework e codice non gestito e agevolare il percorso di migrazione, Common Language Runtime nasconde ai client e ai server le differenze di questi modelli a oggetti.</span><span class="sxs-lookup"><span data-stu-id="3a45d-105">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>

<span data-ttu-id="3a45d-106">Il codice eseguito sotto il controllo del runtime viene definito codice gestito.</span><span class="sxs-lookup"><span data-stu-id="3a45d-106">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="3a45d-107">Al contrario, il codice eseguito esternamente al runtime viene definito codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="3a45d-107">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="3a45d-108">Esempi di codice non gestito sono i componenti COM, le interfacce ActiveX e le funzioni dell'API Windows.</span><span class="sxs-lookup"><span data-stu-id="3a45d-108">COM components, ActiveX interfaces, and Windows API functions are examples of unmanaged code.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3a45d-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3a45d-109">In this section</span></span>

[<span data-ttu-id="3a45d-110">Esposizione di componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3a45d-110">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)  
<span data-ttu-id="3a45d-111">Descrive come usare componenti COM da applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a45d-111">Describes how to use COM components from .NET Framework applications.</span></span>

[<span data-ttu-id="3a45d-112">Esposizione di componenti .NET Framework a COM</span><span class="sxs-lookup"><span data-stu-id="3a45d-112">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)  
<span data-ttu-id="3a45d-113">Descrive come usare componenti .NET Framework da applicazioni COM.</span><span class="sxs-lookup"><span data-stu-id="3a45d-113">Describes how to use .NET Framework components from COM applications.</span></span>

[<span data-ttu-id="3a45d-114">Utilizzo di funzioni di DLL non gestite</span><span class="sxs-lookup"><span data-stu-id="3a45d-114">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
<span data-ttu-id="3a45d-115">Descrive come chiamare funzioni di DLL non gestite con platform invoke.</span><span class="sxs-lookup"><span data-stu-id="3a45d-115">Describes how to call unmanaged DLL functions using platform invoke.</span></span>

[<span data-ttu-id="3a45d-116">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="3a45d-116">Interop Marshaling</span></span>](interop-marshaling.md)  
<span data-ttu-id="3a45d-117">Descrive il marshalling per l'interoperabilità COM e platform invoke.</span><span class="sxs-lookup"><span data-stu-id="3a45d-117">Describes marshaling for COM interop and platform invoke.</span></span>

[<span data-ttu-id="3a45d-118">Procedura: Eseguire il mapping di HRESULT ed eccezioni</span><span class="sxs-lookup"><span data-stu-id="3a45d-118">How to: Map HRESULTs and Exceptions</span></span>](how-to-map-hresults-and-exceptions.md)  
<span data-ttu-id="3a45d-119">Descrive il mapping tra eccezioni e valori HRESULT.</span><span class="sxs-lookup"><span data-stu-id="3a45d-119">Describes the mapping between exceptions and HRESULTs.</span></span>

[<span data-ttu-id="3a45d-120">Wrapper COM</span><span class="sxs-lookup"><span data-stu-id="3a45d-120">COM Wrappers</span></span>](com-wrappers.md)  
<span data-ttu-id="3a45d-121">Descrive i wrapper forniti dall'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="3a45d-121">Describes the wrappers provided by COM interop.</span></span>

[<span data-ttu-id="3a45d-122">Equivalenza del tipo e tipi di interoperabilità incorporati</span><span class="sxs-lookup"><span data-stu-id="3a45d-122">Type Equivalence and Embedded Interop Types</span></span>](type-equivalence-and-embedded-interop-types.md)  
<span data-ttu-id="3a45d-123">Descrive il modo in cui le informazioni sui tipi COM sono incorporate negli assembly e come Common Language Runtime determina l'equivalenza dei tipi COM incorporati.</span><span class="sxs-lookup"><span data-stu-id="3a45d-123">Describes how type information for COM types is embedded in assemblies, and how the common language runtime determines the equivalence of embedded COM types.</span></span>

[<span data-ttu-id="3a45d-124">Procedura: Generare assembly di interoperabilità primari tramite Tlbimp.exe</span><span class="sxs-lookup"><span data-stu-id="3a45d-124">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
<span data-ttu-id="3a45d-125">Descrive come generare assembly di interoperabilità primari usando *Tlbimp.exe* (strumento di importazione di librerie dei tipi).</span><span class="sxs-lookup"><span data-stu-id="3a45d-125">Describes how to produce primary interop assemblies using *Tlbimp.exe* (Type Library Importer).</span></span>

[<span data-ttu-id="3a45d-126">Procedura: Registrare assembly di interoperabilità primari</span><span class="sxs-lookup"><span data-stu-id="3a45d-126">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)  
<span data-ttu-id="3a45d-127">Descrive come registrare gli assembly di interoperabilità primari prima di potervi fare riferimento nei progetti.</span><span class="sxs-lookup"><span data-stu-id="3a45d-127">Describes how to register the primary interop assemblies before you can reference them in your projects.</span></span>

[<span data-ttu-id="3a45d-128">Interoperabilità COM senza registrazione</span><span class="sxs-lookup"><span data-stu-id="3a45d-128">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)  
<span data-ttu-id="3a45d-129">Descrive come l'interoperabilità COM consente di attivare componenti senza usare il Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="3a45d-129">Describes how COM interop can activate components without using the Windows registry.</span></span>

[<span data-ttu-id="3a45d-130">Procedura: Configurare i componenti COM basati su .NET Framework per l'attivazione senza registrazione</span><span class="sxs-lookup"><span data-stu-id="3a45d-130">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>](configure-net-framework-based-com-components-for-reg.md)  
<span data-ttu-id="3a45d-131">Descrive come creare un manifesto dell'applicazione e come creare e incorporare un manifesto del componente.</span><span class="sxs-lookup"><span data-stu-id="3a45d-131">Describes how to create an application manifest and how to create and embed a component manifest.</span></span>
