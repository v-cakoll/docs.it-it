---
title: Librerie di classi e API aggiuntive
ms.date: 11/19/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: abf7fd20988ebaaaf1a40ccc168c636fd0dacc1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155908"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="e0ed2-102">Librerie di classi e API aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e0ed2-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="e0ed2-103">.NET Framework è in continua evoluzione.</span><span class="sxs-lookup"><span data-stu-id="e0ed2-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="e0ed2-104">Per migliorare lo sviluppo multipiattaforma e introdurre nuove funzionalità in anticipo, nuove funzionalità vengono rilasciate fuori banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="e0ed2-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="e0ed2-105">Questo argomento elenca i progetti fuori banda (OOB) per i quali viene fornita la documentazione.</span><span class="sxs-lookup"><span data-stu-id="e0ed2-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="e0ed2-106">Inoltre, alcune librerie sono destinate a piattaforme o implementazioni specifiche di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e0ed2-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="e0ed2-107">Ad esempio, <xref:System.Text.CodePagesEncodingProvider> la classe rende le codifiche della tabella codici disponibili per le app UWP sviluppate con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e0ed2-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="e0ed2-108">Questo argomento include anche un elenco di queste librerie.</span><span class="sxs-lookup"><span data-stu-id="e0ed2-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="e0ed2-109">Progetti OOB</span><span class="sxs-lookup"><span data-stu-id="e0ed2-109">OOB projects</span></span>
  
| <span data-ttu-id="e0ed2-110">Project</span><span class="sxs-lookup"><span data-stu-id="e0ed2-110">Project</span></span> | <span data-ttu-id="e0ed2-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0ed2-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="e0ed2-112">Fornisce raccolte thread-safe e che non modificano mai il contenuto.</span><span class="sxs-lookup"><span data-stu-id="e0ed2-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="e0ed2-113">Fornisce un gestore di messaggi per <xref:System.Net.Http.HttpClient> basato sull'interfaccia WinHTTP di Windows.</span><span class="sxs-lookup"><span data-stu-id="e0ed2-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="e0ed2-114">Fornisce una libreria di tipi di vettori in grado di sfruttare l'accelerazione basata su hardware SIMD.</span><span class="sxs-lookup"><span data-stu-id="e0ed2-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>|
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="e0ed2-115">La libreria del flusso di dati TPL fornisce i componenti del flusso di dati per aumentare l'affidabilità delle applicazioni abilitate per la concorrenza.</span><span class="sxs-lookup"><span data-stu-id="e0ed2-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="e0ed2-116">Librerie specifiche della piattaforma</span><span class="sxs-lookup"><span data-stu-id="e0ed2-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="e0ed2-117">Project</span><span class="sxs-lookup"><span data-stu-id="e0ed2-117">Project</span></span> | <span data-ttu-id="e0ed2-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0ed2-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="e0ed2-119">Estende <xref:System.Text.EncodingProvider> la classe per rendere le codifiche della tabella codici disponibili per le app destinate alla piattaforma Windows universale.</span><span class="sxs-lookup"><span data-stu-id="e0ed2-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="e0ed2-120">API private</span><span class="sxs-lookup"><span data-stu-id="e0ed2-120">Private APIs</span></span>  

<span data-ttu-id="e0ed2-121">Queste API supportano l'infrastruttura del prodotto e non sono progettate/supportate per l'uso direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="e0ed2-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="e0ed2-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Proprietà</span><span class="sxs-lookup"><span data-stu-id="e0ed2-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="e0ed2-123">Metodo System.Exception.PrepForRemoting</span><span class="sxs-lookup"><span data-stu-id="e0ed2-123">System.Exception.PrepForRemoting Method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="e0ed2-124">Proprietà System.Data.SqlTypes.SqlChars.Stream</span><span class="sxs-lookup"><span data-stu-id="e0ed2-124">System.Data.SqlTypes.SqlChars.Stream Property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="e0ed2-125">Costruttore System.Data.SqlTypes.SqlStreamChars</span><span class="sxs-lookup"><span data-stu-id="e0ed2-125">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="e0ed2-126">Proprietà System.Data.SqlTypes.SqlStreamChars.CanSeek</span><span class="sxs-lookup"><span data-stu-id="e0ed2-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="e0ed2-127">Proprietà System.Data.SqlTypes.SqlStreamChars.IsNull</span><span class="sxs-lookup"><span data-stu-id="e0ed2-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="e0ed2-128">Proprietà System.Data.SqlTypes.SqlStreamChars.Length</span><span class="sxs-lookup"><span data-stu-id="e0ed2-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="e0ed2-129">Metodo System.Data.SqlTypes.SqlStreamChars.Close</span><span class="sxs-lookup"><span data-stu-id="e0ed2-129">System.Data.SqlTypes.SqlStreamChars.Close Method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="e0ed2-130">Metodo System.Data.SqlTypes.SqlStreamChars.Dispose</span><span class="sxs-lookup"><span data-stu-id="e0ed2-130">System.Data.SqlTypes.SqlStreamChars.Dispose Method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="e0ed2-131">Metodo System.Data.SqlTypes.SqlStreamChars.Flush</span><span class="sxs-lookup"><span data-stu-id="e0ed2-131">System.Data.SqlTypes.SqlStreamChars.Flush Method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="e0ed2-132">Metodo System.Data.SqlTypes.SqlStreamChars.Read</span><span class="sxs-lookup"><span data-stu-id="e0ed2-132">System.Data.SqlTypes.SqlStreamChars.Read Method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="e0ed2-133">Metodo System.Data.SqlTypes.SqlStreamChars.Seek</span><span class="sxs-lookup"><span data-stu-id="e0ed2-133">System.Data.SqlTypes.SqlStreamChars.Seek Method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="e0ed2-134">Metodo System.Data.SqlTypes.SqlStreamChars.SetLength</span><span class="sxs-lookup"><span data-stu-id="e0ed2-134">System.Data.SqlTypes.SqlStreamChars.SetLength Method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="e0ed2-135">Metodo System.Data.SqlTypes.SqlStreamChars.Write</span><span class="sxs-lookup"><span data-stu-id="e0ed2-135">System.Data.SqlTypes.SqlStreamChars.Write Method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="e0ed2-136">Metodo System.IO.MemoryStream.InternalGetOriginAndLength</span><span class="sxs-lookup"><span data-stu-id="e0ed2-136">System.IO.MemoryStream.InternalGetOriginAndLength Method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="e0ed2-137">Classe System.Net.Connection</span><span class="sxs-lookup"><span data-stu-id="e0ed2-137">System.Net.Connection Class</span></span>](connection.md)
* [<span data-ttu-id="e0ed2-138">Campo WriteList System.Net.Connection.m\_</span><span class="sxs-lookup"><span data-stu-id="e0ed2-138">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md)
* [<span data-ttu-id="e0ed2-139">Classe System.Net.ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="e0ed2-139">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md)
* [<span data-ttu-id="e0ed2-140">System.Net.ConnectionGroup.m\_Campo ConnectionList</span><span class="sxs-lookup"><span data-stu-id="e0ed2-140">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="e0ed2-141">Proprietà System.Net.ConnectStream.Connection</span><span class="sxs-lookup"><span data-stu-id="e0ed2-141">System.Net.ConnectStream.Connection Property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="e0ed2-142">Classe System.Net.CoreResponseData</span><span class="sxs-lookup"><span data-stu-id="e0ed2-142">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="e0ed2-143">System.Net.CoreResponseData.m\_ResponseHeaders Campo</span><span class="sxs-lookup"><span data-stu-id="e0ed2-143">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="e0ed2-144">System.Net.CoreResponseData.m\_Campo StatusCode</span><span class="sxs-lookup"><span data-stu-id="e0ed2-144">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="e0ed2-145">System.Net.HttpWebRequest. \_AutoRedirects Campo</span><span class="sxs-lookup"><span data-stu-id="e0ed2-145">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md)
* [<span data-ttu-id="e0ed2-146">System.Net.HttpWebRequest. \_Campo CoreResponse</span><span class="sxs-lookup"><span data-stu-id="e0ed2-146">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="e0ed2-147">System.Net.HttpWebRequest. \_HttpResponse Campo</span><span class="sxs-lookup"><span data-stu-id="e0ed2-147">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md)
* [<span data-ttu-id="e0ed2-148">Proprietà System.Net.PooledStream.NetworkStream</span><span class="sxs-lookup"><span data-stu-id="e0ed2-148">System.Net.PooledStream.NetworkStream Property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="e0ed2-149">Classe System.Net.RtcState</span><span class="sxs-lookup"><span data-stu-id="e0ed2-149">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="e0ed2-150">System.Net.ServicePoint.m\_ConnectionGroupList Campo</span><span class="sxs-lookup"><span data-stu-id="e0ed2-150">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="e0ed2-151">Campo ServicePointTable di System.Net.ServicePointManager.s\_</span><span class="sxs-lookup"><span data-stu-id="e0ed2-151">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="e0ed2-152">Campo System.Net.TlsStream.m_Worker</span><span class="sxs-lookup"><span data-stu-id="e0ed2-152">System.Net.TlsStream.m_Worker Field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="e0ed2-153">Proprietà System.Net.Security.SslState.SslProtocol</span><span class="sxs-lookup"><span data-stu-id="e0ed2-153">System.Net.Security.SslState.SslProtocol Property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="e0ed2-154">Metodo System.ServiceModel.Channels.Message.BodyToString</span><span class="sxs-lookup"><span data-stu-id="e0ed2-154">System.ServiceModel.Channels.Message.BodyToString Method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="e0ed2-155">Metodo System.ServiceModel.Channels.Message.WriteStartHeaders</span><span class="sxs-lookup"><span data-stu-id="e0ed2-155">System.ServiceModel.Channels.Message.WriteStartHeaders Method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="e0ed2-156">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Campo</span><span class="sxs-lookup"><span data-stu-id="e0ed2-156">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="e0ed2-157">Classe System.Windows.Forms.Design.DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="e0ed2-157">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="e0ed2-158">Classe System.Windows.Forms.Design.DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="e0ed2-158">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="e0ed2-159">Metodo System.Xml.XmlReader.CreateSqlReader</span><span class="sxs-lookup"><span data-stu-id="e0ed2-159">System.Xml.XmlReader.CreateSqlReader Method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="e0ed2-160">Adodb. Interfaccia di connessione</span><span class="sxs-lookup"><span data-stu-id="e0ed2-160">adodb.Connection Interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="e0ed2-161">Adodb. Enumerazione EventReason</span><span class="sxs-lookup"><span data-stu-id="e0ed2-161">adodb.EventReason Enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="e0ed2-162">Adodb. Enumerazione EventStatus</span><span class="sxs-lookup"><span data-stu-id="e0ed2-162">adodb.EventStatus Enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="e0ed2-163">stdole. Struttura DISPPARAMS</span><span class="sxs-lookup"><span data-stu-id="e0ed2-163">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="e0ed2-164">stdole. ExCEPINFO Struttura</span><span class="sxs-lookup"><span data-stu-id="e0ed2-164">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="e0ed2-165">stdole. IFont.Name Proprietà</span><span class="sxs-lookup"><span data-stu-id="e0ed2-165">stdole.IFont.Name Property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="e0ed2-166">stdole. Interfaccia IFontDisp</span><span class="sxs-lookup"><span data-stu-id="e0ed2-166">stdole.IFontDisp Interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="e0ed2-167">stdole. IPicture.Handle Proprietà</span><span class="sxs-lookup"><span data-stu-id="e0ed2-167">stdole.IPicture.Handle Property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="e0ed2-168">stdole. IPictureDisp.Handle Proprietà</span><span class="sxs-lookup"><span data-stu-id="e0ed2-168">stdole.IPictureDisp.Handle Property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="e0ed2-169">stdole. Interfaccia StdFont</span><span class="sxs-lookup"><span data-stu-id="e0ed2-169">stdole.StdFont Interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="e0ed2-170">stdole. Interfaccia StdPicture</span><span class="sxs-lookup"><span data-stu-id="e0ed2-170">stdole.StdPicture Interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="e0ed2-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0ed2-171">See also</span></span>

* [<span data-ttu-id="e0ed2-172">.NET Framework e rilascio fuori programma</span><span class="sxs-lookup"><span data-stu-id="e0ed2-172">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
