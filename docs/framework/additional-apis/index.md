---
title: Librerie di classi e API aggiuntive
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c22de3ed401e0be10b155649395da43cedb35e6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="088b4-102">Librerie di classi e API aggiuntive</span><span class="sxs-lookup"><span data-stu-id="088b4-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="088b4-103">Poiché .NET Framework è in costante evoluzione, vengono rilasciate nuove funzionalità fuori programma (OOB) per migliorare lo sviluppo multipiattaforma o introdurre nuove funzionalità in anteprima per i clienti.</span><span class="sxs-lookup"><span data-stu-id="088b4-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="088b4-104">Questo argomento elenca i progetti fuori banda (OOB) per i quali viene fornita la documentazione.</span><span class="sxs-lookup"><span data-stu-id="088b4-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="088b4-105">Inoltre, alcune librerie sono destinate a piattaforme o implementazioni specifiche di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="088b4-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="088b4-106">Ad esempio, il <xref:System.Text.CodePagesEncodingProvider> rende codifiche delle tabelle codici di codice disponibili per App UWP sviluppata con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="088b4-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="088b4-107">Questo argomento include anche un elenco di queste librerie.</span><span class="sxs-lookup"><span data-stu-id="088b4-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="088b4-108">Progetti OOB</span><span class="sxs-lookup"><span data-stu-id="088b4-108">OOB projects</span></span>
  
| <span data-ttu-id="088b4-109">Progetto</span><span class="sxs-lookup"><span data-stu-id="088b4-109">Project</span></span> | <span data-ttu-id="088b4-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="088b4-110">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="088b4-111">Fornisce raccolte thread-safe e che non modificano mai il contenuto.</span><span class="sxs-lookup"><span data-stu-id="088b4-111">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="088b4-112">Fornisce un gestore di messaggi per <xref:System.Net.Http.HttpClient> basato sull'interfaccia WinHTTP di Windows.</span><span class="sxs-lookup"><span data-stu-id="088b4-112">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="088b4-113">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="088b4-113">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="088b4-114">Fornisce una libreria di tipi di vettori in grado di sfruttare l'accelerazione basata su hardware SIMD.</span><span class="sxs-lookup"><span data-stu-id="088b4-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="088b4-115">La libreria del flusso di dati TPL fornisce i componenti del flusso di dati per aumentare l'affidabilità delle applicazioni abilitate per la concorrenza.</span><span class="sxs-lookup"><span data-stu-id="088b4-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="088b4-116">Librerie specifiche della piattaforma</span><span class="sxs-lookup"><span data-stu-id="088b4-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="088b4-117">Progetto</span><span class="sxs-lookup"><span data-stu-id="088b4-117">Project</span></span> | <span data-ttu-id="088b4-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="088b4-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="088b4-119">Estende la <xref:System.Text.EncodingProvider> classe per rendere disponibili per le applicazioni che usano la piattaforma Windows universale codifiche delle tabelle codici di codice.</span><span class="sxs-lookup"><span data-stu-id="088b4-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="088b4-120">API private</span><span class="sxs-lookup"><span data-stu-id="088b4-120">Private APIs</span></span>  

<span data-ttu-id="088b4-121">Queste API supportano l'infrastruttura del prodotto e non sono progettate/supportate per l'uso direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="088b4-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="088b4-122">Nome dell'API</span><span class="sxs-lookup"><span data-stu-id="088b4-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="088b4-123">Classe System.Net.Connection</span><span class="sxs-lookup"><span data-stu-id="088b4-123">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="088b4-124">System.Net.Connection.m\_WriteList campo</span><span class="sxs-lookup"><span data-stu-id="088b4-124">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="088b4-125">Classe System.Net.ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="088b4-125">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="088b4-126">System.Net.ConnectionGroup.m\_ConnectionList campo</span><span class="sxs-lookup"><span data-stu-id="088b4-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="088b4-127">System.NET. HttpWebRequest. \_HttpResponse campo</span><span class="sxs-lookup"><span data-stu-id="088b4-127">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="088b4-128">System.NET. HttpWebRequest. \_AutoRedirects campo</span><span class="sxs-lookup"><span data-stu-id="088b4-128">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="088b4-129">System.Net.ServicePoint.m\_ConnectionGroupList campo</span><span class="sxs-lookup"><span data-stu-id="088b4-129">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="088b4-130">System.Net.ServicePointManager.s\_ServicePointTable campo</span><span class="sxs-lookup"><span data-stu-id="088b4-130">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="088b4-131">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes campo</span><span class="sxs-lookup"><span data-stu-id="088b4-131">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="088b4-132">Classe System.Windows.Forms.Design.DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="088b4-132">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="088b4-133">Classe System.Windows.Forms.Design.DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="088b4-133">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="088b4-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="088b4-134">See also</span></span>

[<span data-ttu-id="088b4-135">.NET Framework e rilascio fuori programma</span><span class="sxs-lookup"><span data-stu-id="088b4-135">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
