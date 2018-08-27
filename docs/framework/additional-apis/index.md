---
title: Librerie di classi e API aggiuntive
ms.date: 01/29/2018
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 049268c29946e95ca7bb194f6cae38baf8f060f6
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933530"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="daf3e-102">Librerie di classi e API aggiuntive</span><span class="sxs-lookup"><span data-stu-id="daf3e-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="daf3e-103">.NET Framework è in costante evoluzione.</span><span class="sxs-lookup"><span data-stu-id="daf3e-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="daf3e-104">Per migliorare lo sviluppo multipiattaforma e introdurre nuove funzionalità all'inizio, vengono rilasciate nuove funzionalità fuori banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="daf3e-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="daf3e-105">Questo argomento elenca i progetti fuori banda (OOB) per i quali viene fornita la documentazione.</span><span class="sxs-lookup"><span data-stu-id="daf3e-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="daf3e-106">Inoltre, alcune librerie sono destinate a piattaforme o implementazioni specifiche di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="daf3e-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="daf3e-107">Ad esempio, il <xref:System.Text.CodePagesEncodingProvider> classe rende codifiche della tabella codici disponibili per le app UWP sviluppate usando .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="daf3e-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="daf3e-108">Questo argomento include anche un elenco di queste librerie.</span><span class="sxs-lookup"><span data-stu-id="daf3e-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="daf3e-109">Progetti OOB</span><span class="sxs-lookup"><span data-stu-id="daf3e-109">OOB projects</span></span>
  
| <span data-ttu-id="daf3e-110">Progetto</span><span class="sxs-lookup"><span data-stu-id="daf3e-110">Project</span></span> | <span data-ttu-id="daf3e-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="daf3e-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="daf3e-112">Fornisce raccolte thread-safe e che non modificano mai il contenuto.</span><span class="sxs-lookup"><span data-stu-id="daf3e-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="daf3e-113">Fornisce un gestore di messaggi per <xref:System.Net.Http.HttpClient> basato sull'interfaccia WinHTTP di Windows.</span><span class="sxs-lookup"><span data-stu-id="daf3e-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="daf3e-114">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="daf3e-114">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="daf3e-115">Fornisce una libreria di tipi di vettori in grado di sfruttare l'accelerazione basata su hardware SIMD.</span><span class="sxs-lookup"><span data-stu-id="daf3e-115">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="daf3e-116">La libreria del flusso di dati TPL fornisce i componenti del flusso di dati per aumentare l'affidabilità delle applicazioni abilitate per la concorrenza.</span><span class="sxs-lookup"><span data-stu-id="daf3e-116">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="daf3e-117">Librerie specifiche della piattaforma</span><span class="sxs-lookup"><span data-stu-id="daf3e-117">Platform-specific libraries</span></span>
  
| <span data-ttu-id="daf3e-118">Progetto</span><span class="sxs-lookup"><span data-stu-id="daf3e-118">Project</span></span> | <span data-ttu-id="daf3e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="daf3e-119">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="daf3e-120">Estende il <xref:System.Text.EncodingProvider> classe per rendere disponibili per le app destinate a Universal Windows Platform codifiche della tabella codici.</span><span class="sxs-lookup"><span data-stu-id="daf3e-120">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="daf3e-121">API private</span><span class="sxs-lookup"><span data-stu-id="daf3e-121">Private APIs</span></span>  

<span data-ttu-id="daf3e-122">Queste API supportano l'infrastruttura del prodotto e non sono progettate/supportate per l'uso direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="daf3e-122">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="daf3e-123">Nome dell'API</span><span class="sxs-lookup"><span data-stu-id="daf3e-123">API Name</span></span> |
| -------- |
| [<span data-ttu-id="daf3e-124">Classe System.Net.Connection</span><span class="sxs-lookup"><span data-stu-id="daf3e-124">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="daf3e-125">System.Net.Connection.m\_WriteList campo</span><span class="sxs-lookup"><span data-stu-id="daf3e-125">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="daf3e-126">Classe System.Net.ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="daf3e-126">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="daf3e-127">System.Net.ConnectionGroup.m\_ConnectionList Field</span><span class="sxs-lookup"><span data-stu-id="daf3e-127">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="daf3e-128">Classe System.Net.CoreResponseData</span><span class="sxs-lookup"><span data-stu-id="daf3e-128">System.Net.CoreResponseData Class</span></span>](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [<span data-ttu-id="daf3e-129">System.Net.CoreResponseData.m\_ResponseHeaders Field</span><span class="sxs-lookup"><span data-stu-id="daf3e-129">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="daf3e-130">System.Net.CoreResponseData.m\_StatusCode Field</span><span class="sxs-lookup"><span data-stu-id="daf3e-130">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="daf3e-131">System.NET. HttpWebRequest. \_Campo AutoRedirects</span><span class="sxs-lookup"><span data-stu-id="daf3e-131">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="daf3e-132">System.NET. HttpWebRequest. \_Campo CoreResponse</span><span class="sxs-lookup"><span data-stu-id="daf3e-132">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="daf3e-133">System.NET. HttpWebRequest. \_HttpResponse campo</span><span class="sxs-lookup"><span data-stu-id="daf3e-133">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="daf3e-134">System.Net.ServicePoint.m\_ConnectionGroupList Field</span><span class="sxs-lookup"><span data-stu-id="daf3e-134">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="daf3e-135">System.Net.ServicePointManager.s\_ServicePointTable Field</span><span class="sxs-lookup"><span data-stu-id="daf3e-135">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="daf3e-136">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span><span class="sxs-lookup"><span data-stu-id="daf3e-136">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="daf3e-137">Classe System.Windows.Forms.Design.DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="daf3e-137">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="daf3e-138">Classe System.Windows.Forms.Design.DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="daf3e-138">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="daf3e-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="daf3e-139">See also</span></span>

[<span data-ttu-id="daf3e-140">.NET Framework e rilascio fuori programma</span><span class="sxs-lookup"><span data-stu-id="daf3e-140">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
