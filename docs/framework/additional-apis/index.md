---
title: Librerie di classi e API aggiuntive | Microsoft Docs
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: 12
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: b53b8acc2a6c56db6a9d8a9b7c685a2d400a53e1
ms.openlocfilehash: 34815268b707aa70d174a1bbc04c32276db8412d
ms.contentlocale: it-it
ms.lasthandoff: 05/02/2017

---

# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="db968-102">Librerie di classi e API aggiuntive</span><span class="sxs-lookup"><span data-stu-id="db968-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="db968-103">Poiché .NET Framework è in costante evoluzione, vengono rilasciate nuove funzionalità fuori programma (OOB) per migliorare lo sviluppo multipiattaforma o introdurre nuove funzionalità in anteprima per i clienti.</span><span class="sxs-lookup"><span data-stu-id="db968-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="db968-104">Questo argomento elenca i progetti fuori banda (OOB) per i quali viene fornita la documentazione.</span><span class="sxs-lookup"><span data-stu-id="db968-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="db968-105">Inoltre, alcune librerie sono destinate a piattaforme o implementazioni specifiche di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db968-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="db968-106">Ad esempio, la classe <xref:System.Text.CodePagesEncodingProvider> rende disponibili le codifiche della tabella codici per le app UWP sviluppate con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db968-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="db968-107">Questo argomento include anche un elenco di queste librerie.</span><span class="sxs-lookup"><span data-stu-id="db968-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="db968-108">Progetti OOB</span><span class="sxs-lookup"><span data-stu-id="db968-108">OOB projects</span></span>
  
| <span data-ttu-id="db968-109">Progetto</span><span class="sxs-lookup"><span data-stu-id="db968-109">Project</span></span> | <span data-ttu-id="db968-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db968-110">Description</span></span> |  
| ------- | ----------- |  
| <span data-ttu-id="db968-111"><xref:System.Collections.Immutable></span><span class="sxs-lookup"><span data-stu-id="db968-111"><xref:System.Collections.Immutable></span></span> | <span data-ttu-id="db968-112">Fornisce raccolte thread-safe e che non modificano mai il contenuto.</span><span class="sxs-lookup"><span data-stu-id="db968-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <span data-ttu-id="db968-113"><xref:System.Net.Http.WinHttpHandler></span><span class="sxs-lookup"><span data-stu-id="db968-113"><xref:System.Net.Http.WinHttpHandler></span></span> | <span data-ttu-id="db968-114">Fornisce un gestore di messaggi per <xref:System.Net.Http.HttpClient> basato sull'interfaccia WinHTTP di Windows.</span><span class="sxs-lookup"><span data-stu-id="db968-114">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="db968-115">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="db968-115">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="db968-116">Fornisce una libreria di tipi di vettori in grado di sfruttare l'accelerazione basata su hardware SIMD.</span><span class="sxs-lookup"><span data-stu-id="db968-116">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <span data-ttu-id="db968-117"><xref:System.Threading.Tasks.Dataflow></span><span class="sxs-lookup"><span data-stu-id="db968-117"><xref:System.Threading.Tasks.Dataflow></span></span> | <span data-ttu-id="db968-118">La libreria del flusso di dati TPL fornisce i componenti del flusso di dati per aumentare l'affidabilità delle applicazioni abilitate per la concorrenza.</span><span class="sxs-lookup"><span data-stu-id="db968-118">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="db968-119">Librerie specifiche della piattaforma</span><span class="sxs-lookup"><span data-stu-id="db968-119">Platform-specific libraries</span></span>
  
| <span data-ttu-id="db968-120">Progetto</span><span class="sxs-lookup"><span data-stu-id="db968-120">Project</span></span> | <span data-ttu-id="db968-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db968-121">Description</span></span> |  
| ------- | ----------- |  
| <span data-ttu-id="db968-122"><xref:System.Text.CodePagesEncodingProvider></span><span class="sxs-lookup"><span data-stu-id="db968-122"><xref:System.Text.CodePagesEncodingProvider></span></span> | <span data-ttu-id="db968-123">Estende la classe <xref:System.Text.EncodingProvider> per rendere disponibili le codifiche della tabella codice per le app che usano la piattaforma UWP (Universal Windows Platform).</span><span class="sxs-lookup"><span data-stu-id="db968-123">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="db968-124">API private</span><span class="sxs-lookup"><span data-stu-id="db968-124">Private APIs</span></span>  

<span data-ttu-id="db968-125">Queste API supportano l'infrastruttura del prodotto e non sono progettate/supportate per l'uso direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="db968-125">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="db968-126">Nome dell'API</span><span class="sxs-lookup"><span data-stu-id="db968-126">API Name</span></span> |  
| -------- |  
| [<span data-ttu-id="db968-127">Campo s_isDebuggerCheckDisabledForTestPurposes</span><span class="sxs-lookup"><span data-stu-id="db968-127">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |  
| [<span data-ttu-id="db968-128">Classe DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="db968-128">DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |  
| [<span data-ttu-id="db968-129">Classe DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="db968-129">DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |  
  
## <a name="see-also"></a><span data-ttu-id="db968-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db968-130">See also</span></span>

[<span data-ttu-id="db968-131">.NET Framework e rilascio fuori programma</span><span class="sxs-lookup"><span data-stu-id="db968-131">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)

