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
ms.openlocfilehash: bdba02feb8cacc6ab1886c12f88716184aa2a81a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752429"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="bd1ce-102">Librerie di classi e API aggiuntive</span><span class="sxs-lookup"><span data-stu-id="bd1ce-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="bd1ce-103">Poiché .NET Framework è in costante evoluzione, vengono rilasciate nuove funzionalità fuori programma (OOB) per migliorare lo sviluppo multipiattaforma o introdurre nuove funzionalità in anteprima per i clienti.</span><span class="sxs-lookup"><span data-stu-id="bd1ce-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="bd1ce-104">Questo argomento elenca i progetti fuori banda (OOB) per i quali viene fornita la documentazione.</span><span class="sxs-lookup"><span data-stu-id="bd1ce-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="bd1ce-105">Inoltre, alcune librerie sono destinate a piattaforme o implementazioni specifiche di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bd1ce-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="bd1ce-106">Ad esempio, il <xref:System.Text.CodePagesEncodingProvider> rende codifiche delle tabelle codici di codice disponibili per App UWP sviluppata con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bd1ce-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="bd1ce-107">Questo argomento include anche un elenco di queste librerie.</span><span class="sxs-lookup"><span data-stu-id="bd1ce-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="bd1ce-108">Progetti OOB</span><span class="sxs-lookup"><span data-stu-id="bd1ce-108">OOB projects</span></span>
  
| <span data-ttu-id="bd1ce-109">Progetto</span><span class="sxs-lookup"><span data-stu-id="bd1ce-109">Project</span></span> | <span data-ttu-id="bd1ce-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd1ce-110">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="bd1ce-111">Fornisce raccolte thread-safe e che non modificano mai il contenuto.</span><span class="sxs-lookup"><span data-stu-id="bd1ce-111">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="bd1ce-112">Fornisce un gestore di messaggi per <xref:System.Net.Http.HttpClient> basato sull'interfaccia WinHTTP di Windows.</span><span class="sxs-lookup"><span data-stu-id="bd1ce-112">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="bd1ce-113">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="bd1ce-113">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="bd1ce-114">Fornisce una libreria di tipi di vettori in grado di sfruttare l'accelerazione basata su hardware SIMD.</span><span class="sxs-lookup"><span data-stu-id="bd1ce-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="bd1ce-115">La libreria del flusso di dati TPL fornisce i componenti del flusso di dati per aumentare l'affidabilità delle applicazioni abilitate per la concorrenza.</span><span class="sxs-lookup"><span data-stu-id="bd1ce-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="bd1ce-116">Librerie specifiche della piattaforma</span><span class="sxs-lookup"><span data-stu-id="bd1ce-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="bd1ce-117">Progetto</span><span class="sxs-lookup"><span data-stu-id="bd1ce-117">Project</span></span> | <span data-ttu-id="bd1ce-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd1ce-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="bd1ce-119">Estende la <xref:System.Text.EncodingProvider> classe per rendere disponibili per le applicazioni che usano la piattaforma Windows universale codifiche delle tabelle codici di codice.</span><span class="sxs-lookup"><span data-stu-id="bd1ce-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="bd1ce-120">API private</span><span class="sxs-lookup"><span data-stu-id="bd1ce-120">Private APIs</span></span>  

<span data-ttu-id="bd1ce-121">Queste API supportano l'infrastruttura del prodotto e non sono progettate/supportate per l'uso direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="bd1ce-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="bd1ce-122">Nome dell'API</span><span class="sxs-lookup"><span data-stu-id="bd1ce-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="bd1ce-123">Classe System.Net.Connection</span><span class="sxs-lookup"><span data-stu-id="bd1ce-123">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="bd1ce-124">System.Net.Connection.m\_WriteList campo</span><span class="sxs-lookup"><span data-stu-id="bd1ce-124">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="bd1ce-125">Classe System.Net.ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="bd1ce-125">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="bd1ce-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span><span class="sxs-lookup"><span data-stu-id="bd1ce-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="bd1ce-127">Classe System.Net.CoreResponseData</span><span class="sxs-lookup"><span data-stu-id="bd1ce-127">System.Net.CoreResponseData Class</span></span>](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [<span data-ttu-id="bd1ce-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span><span class="sxs-lookup"><span data-stu-id="bd1ce-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="bd1ce-129">System.Net.CoreResponseData.m\_StatusCode Field</span><span class="sxs-lookup"><span data-stu-id="bd1ce-129">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="bd1ce-130">System.NET. HttpWebRequest. \_AutoRedirects campo</span><span class="sxs-lookup"><span data-stu-id="bd1ce-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="bd1ce-131">System.NET. HttpWebRequest. \_CoreResponse campo</span><span class="sxs-lookup"><span data-stu-id="bd1ce-131">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="bd1ce-132">System.NET. HttpWebRequest. \_HttpResponse campo</span><span class="sxs-lookup"><span data-stu-id="bd1ce-132">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="bd1ce-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span><span class="sxs-lookup"><span data-stu-id="bd1ce-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="bd1ce-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span><span class="sxs-lookup"><span data-stu-id="bd1ce-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="bd1ce-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span><span class="sxs-lookup"><span data-stu-id="bd1ce-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="bd1ce-136">Classe System.Windows.Forms.Design.DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="bd1ce-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="bd1ce-137">Classe System.Windows.Forms.Design.DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="bd1ce-137">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="bd1ce-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd1ce-138">See also</span></span>

[<span data-ttu-id="bd1ce-139">.NET Framework e rilascio fuori programma</span><span class="sxs-lookup"><span data-stu-id="bd1ce-139">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
