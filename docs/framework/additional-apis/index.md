---
title: Librerie di classi e API aggiuntive
ms.date: 10/17/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: 4b47847e9d6e9424d4442d655c40a637383c7229
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847073"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="5020e-102">Librerie di classi e API aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5020e-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="5020e-103">Il .NET Framework è in continua evoluzione.</span><span class="sxs-lookup"><span data-stu-id="5020e-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="5020e-104">Per migliorare lo sviluppo multipiattaforma e introdurre nuove funzionalità in anticipo, le nuove funzionalità vengono rilasciate fuori banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="5020e-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="5020e-105">Questo argomento elenca i progetti fuori banda (OOB) per i quali viene fornita la documentazione.</span><span class="sxs-lookup"><span data-stu-id="5020e-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="5020e-106">Inoltre, alcune librerie sono destinate a piattaforme o implementazioni specifiche di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5020e-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="5020e-107">Ad esempio, la classe <xref:System.Text.CodePagesEncodingProvider> rende disponibili le codifiche della tabella codici per le app UWP sviluppate usando il .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5020e-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="5020e-108">Questo argomento include anche un elenco di queste librerie.</span><span class="sxs-lookup"><span data-stu-id="5020e-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="5020e-109">Progetti OOB</span><span class="sxs-lookup"><span data-stu-id="5020e-109">OOB projects</span></span>
  
| <span data-ttu-id="5020e-110">Progetto</span><span class="sxs-lookup"><span data-stu-id="5020e-110">Project</span></span> | <span data-ttu-id="5020e-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5020e-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="5020e-112">Fornisce raccolte thread-safe e che non modificano mai il contenuto.</span><span class="sxs-lookup"><span data-stu-id="5020e-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="5020e-113">Fornisce un gestore di messaggi per <xref:System.Net.Http.HttpClient> basato sull'interfaccia WinHTTP di Windows.</span><span class="sxs-lookup"><span data-stu-id="5020e-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="5020e-114">Fornisce una libreria di tipi di vettori in grado di sfruttare l'accelerazione basata su hardware SIMD.</span><span class="sxs-lookup"><span data-stu-id="5020e-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="5020e-115">La libreria del flusso di dati TPL fornisce i componenti del flusso di dati per aumentare l'affidabilità delle applicazioni abilitate per la concorrenza.</span><span class="sxs-lookup"><span data-stu-id="5020e-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="5020e-116">Librerie specifiche della piattaforma</span><span class="sxs-lookup"><span data-stu-id="5020e-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="5020e-117">Progetto</span><span class="sxs-lookup"><span data-stu-id="5020e-117">Project</span></span> | <span data-ttu-id="5020e-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5020e-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="5020e-119">Estende la classe <xref:System.Text.EncodingProvider> per rendere disponibili le codifiche della tabella codici per le app destinate al piattaforma UWP (Universal Windows Platform).</span><span class="sxs-lookup"><span data-stu-id="5020e-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="5020e-120">API private</span><span class="sxs-lookup"><span data-stu-id="5020e-120">Private APIs</span></span>  

<span data-ttu-id="5020e-121">Queste API supportano l'infrastruttura del prodotto e non sono progettate/supportate per l'uso direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="5020e-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="5020e-122">Proprietà Microsoft. SqlServer. Server. SmiOrderProperty. Item</span><span class="sxs-lookup"><span data-stu-id="5020e-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="5020e-123">System. Exception. PrepForRemoting, metodo</span><span class="sxs-lookup"><span data-stu-id="5020e-123">System.Exception.PrepForRemoting Method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="5020e-124">Proprietà System. Data. SqlTypes. SqlChars. Stream</span><span class="sxs-lookup"><span data-stu-id="5020e-124">System.Data.SqlTypes.SqlChars.Stream Property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="5020e-125">System. Data. SqlTypes. SqlStreamChars (costruttore)</span><span class="sxs-lookup"><span data-stu-id="5020e-125">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="5020e-126">Proprietà System. Data. SqlTypes. SqlStreamChars. CanSeek</span><span class="sxs-lookup"><span data-stu-id="5020e-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="5020e-127">Proprietà System. Data. SqlTypes. SqlStreamChars. IsNull</span><span class="sxs-lookup"><span data-stu-id="5020e-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="5020e-128">Proprietà System. Data. SqlTypes. SqlStreamChars. length</span><span class="sxs-lookup"><span data-stu-id="5020e-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="5020e-129">System. Data. SqlTypes. SqlStreamChars. Close (metodo)</span><span class="sxs-lookup"><span data-stu-id="5020e-129">System.Data.SqlTypes.SqlStreamChars.Close Method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="5020e-130">System. Data. SqlTypes. SqlStreamChars. Dispose (metodo)</span><span class="sxs-lookup"><span data-stu-id="5020e-130">System.Data.SqlTypes.SqlStreamChars.Dispose Method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="5020e-131">Metodo System. Data. SqlTypes. SqlStreamChars. Flush</span><span class="sxs-lookup"><span data-stu-id="5020e-131">System.Data.SqlTypes.SqlStreamChars.Flush Method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="5020e-132">Metodo System. Data. SqlTypes. SqlStreamChars. Read</span><span class="sxs-lookup"><span data-stu-id="5020e-132">System.Data.SqlTypes.SqlStreamChars.Read Method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="5020e-133">Metodo System. Data. SqlTypes. SqlStreamChars. Seek</span><span class="sxs-lookup"><span data-stu-id="5020e-133">System.Data.SqlTypes.SqlStreamChars.Seek Method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="5020e-134">Metodo System. Data. SqlTypes. SqlStreamChars. selength</span><span class="sxs-lookup"><span data-stu-id="5020e-134">System.Data.SqlTypes.SqlStreamChars.SetLength Method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="5020e-135">Metodo System. Data. SqlTypes. SqlStreamChars. Write</span><span class="sxs-lookup"><span data-stu-id="5020e-135">System.Data.SqlTypes.SqlStreamChars.Write Method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="5020e-136">Classe System .NET. Connection</span><span class="sxs-lookup"><span data-stu-id="5020e-136">System.Net.Connection Class</span></span>](connection.md)
* [<span data-ttu-id="5020e-137">System .NET. Connection. m\_campo di writeback</span><span class="sxs-lookup"><span data-stu-id="5020e-137">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md)
* [<span data-ttu-id="5020e-138">Classe System .NET. ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="5020e-138">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md)
* [<span data-ttu-id="5020e-139">Campo System .NET. ConnectionGroup. m\_ConnectionName</span><span class="sxs-lookup"><span data-stu-id="5020e-139">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="5020e-140">Proprietà System .NET. ConnectStream. Connection</span><span class="sxs-lookup"><span data-stu-id="5020e-140">System.Net.ConnectStream.Connection Property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="5020e-141">Classe System .NET. CoreResponseData</span><span class="sxs-lookup"><span data-stu-id="5020e-141">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="5020e-142">System .NET. CoreResponseData. m\_campo ResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="5020e-142">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="5020e-143">Campo System .NET. CoreResponseData. m\_StatusCode</span><span class="sxs-lookup"><span data-stu-id="5020e-143">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="5020e-144">System .NET. HttpWebRequest.\_campo autodirects</span><span class="sxs-lookup"><span data-stu-id="5020e-144">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md)
* [<span data-ttu-id="5020e-145">Campo System .NET. HttpWebRequest.\_CoreResponse</span><span class="sxs-lookup"><span data-stu-id="5020e-145">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="5020e-146">Campo System .NET. HttpWebRequest.\_HttpResponse</span><span class="sxs-lookup"><span data-stu-id="5020e-146">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md)
* [<span data-ttu-id="5020e-147">Proprietà System .NET. PooledStream. NetworkStream</span><span class="sxs-lookup"><span data-stu-id="5020e-147">System.Net.PooledStream.NetworkStream Property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="5020e-148">Campo System .NET. ServicePoint. m\_ConnectionGroupList</span><span class="sxs-lookup"><span data-stu-id="5020e-148">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="5020e-149">Campo ServicePointTable di System .NET. ServicePointManager. s\_</span><span class="sxs-lookup"><span data-stu-id="5020e-149">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="5020e-150">Campo System .NET. TlsStream. m_Worker</span><span class="sxs-lookup"><span data-stu-id="5020e-150">System.Net.TlsStream.m_Worker Field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="5020e-151">Proprietà System .NET. Security. SslState. SslProtocol</span><span class="sxs-lookup"><span data-stu-id="5020e-151">System.Net.Security.SslState.SslProtocol Property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="5020e-152">System. Windows. Diagnostics. VisualDiagnostics. s\_campo isDebuggerCheckDisabledForTestPurposes</span><span class="sxs-lookup"><span data-stu-id="5020e-152">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="5020e-153">Classe System. Windows. Forms. Design. DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="5020e-153">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="5020e-154">Classe System. Windows. Forms. Design. DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="5020e-154">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="5020e-155">System. XML. XmlReader. CreateSqlReader, metodo</span><span class="sxs-lookup"><span data-stu-id="5020e-155">System.Xml.XmlReader.CreateSqlReader Method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="5020e-156">oggetto ADODB. Interfaccia di connessione</span><span class="sxs-lookup"><span data-stu-id="5020e-156">adodb.Connection Interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="5020e-157">oggetto ADODB. Enumerazione EventReason</span><span class="sxs-lookup"><span data-stu-id="5020e-157">adodb.EventReason Enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="5020e-158">oggetto ADODB. Enumerazione EventStatus</span><span class="sxs-lookup"><span data-stu-id="5020e-158">adodb.EventStatus Enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="5020e-159">stdole. Struttura DISPPARAMS</span><span class="sxs-lookup"><span data-stu-id="5020e-159">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="5020e-160">stdole. Struttura EXCEPINFO</span><span class="sxs-lookup"><span data-stu-id="5020e-160">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="5020e-161">stdole. Proprietà IFont.Name</span><span class="sxs-lookup"><span data-stu-id="5020e-161">stdole.IFont.Name Property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="5020e-162">stdole. Interfaccia IFontDisp</span><span class="sxs-lookup"><span data-stu-id="5020e-162">stdole.IFontDisp Interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="5020e-163">stdole. Proprietà IPicture. handle</span><span class="sxs-lookup"><span data-stu-id="5020e-163">stdole.IPicture.Handle Property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="5020e-164">stdole. Proprietà IPictureDisp. handle</span><span class="sxs-lookup"><span data-stu-id="5020e-164">stdole.IPictureDisp.Handle Property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="5020e-165">stdole. Interfaccia StdFont</span><span class="sxs-lookup"><span data-stu-id="5020e-165">stdole.StdFont Interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="5020e-166">stdole. Interfaccia StdPicture</span><span class="sxs-lookup"><span data-stu-id="5020e-166">stdole.StdPicture Interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="5020e-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5020e-167">See also</span></span>

* [<span data-ttu-id="5020e-168">.NET Framework e rilascio fuori programma</span><span class="sxs-lookup"><span data-stu-id="5020e-168">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
