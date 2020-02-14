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
ms.openlocfilehash: 3a5134aa4407598e223fd2c938bfaac02cf9178c
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215543"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="46fae-102">Librerie di classi e API aggiuntive</span><span class="sxs-lookup"><span data-stu-id="46fae-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="46fae-103">Il .NET Framework è in continua evoluzione.</span><span class="sxs-lookup"><span data-stu-id="46fae-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="46fae-104">Per migliorare lo sviluppo multipiattaforma e introdurre nuove funzionalità in anticipo, le nuove funzionalità vengono rilasciate fuori banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="46fae-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="46fae-105">Questo argomento elenca i progetti fuori banda (OOB) per i quali viene fornita la documentazione.</span><span class="sxs-lookup"><span data-stu-id="46fae-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="46fae-106">Inoltre, alcune librerie sono destinate a piattaforme o implementazioni specifiche di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="46fae-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="46fae-107">Ad esempio, la classe <xref:System.Text.CodePagesEncodingProvider> rende disponibili le codifiche della tabella codici per le app UWP sviluppate usando il .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="46fae-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="46fae-108">Questo argomento include anche un elenco di queste librerie.</span><span class="sxs-lookup"><span data-stu-id="46fae-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="46fae-109">Progetti OOB</span><span class="sxs-lookup"><span data-stu-id="46fae-109">OOB projects</span></span>
  
| <span data-ttu-id="46fae-110">Project</span><span class="sxs-lookup"><span data-stu-id="46fae-110">Project</span></span> | <span data-ttu-id="46fae-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46fae-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="46fae-112">Fornisce raccolte thread-safe e che non modificano mai il contenuto.</span><span class="sxs-lookup"><span data-stu-id="46fae-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="46fae-113">Fornisce un gestore di messaggi per <xref:System.Net.Http.HttpClient> basato sull'interfaccia WinHTTP di Windows.</span><span class="sxs-lookup"><span data-stu-id="46fae-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="46fae-114">Fornisce una libreria di tipi di vettori in grado di sfruttare l'accelerazione basata su hardware SIMD.</span><span class="sxs-lookup"><span data-stu-id="46fae-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="46fae-115">La libreria del flusso di dati TPL fornisce i componenti del flusso di dati per aumentare l'affidabilità delle applicazioni abilitate per la concorrenza.</span><span class="sxs-lookup"><span data-stu-id="46fae-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="46fae-116">Librerie specifiche della piattaforma</span><span class="sxs-lookup"><span data-stu-id="46fae-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="46fae-117">Project</span><span class="sxs-lookup"><span data-stu-id="46fae-117">Project</span></span> | <span data-ttu-id="46fae-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46fae-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="46fae-119">Estende la classe <xref:System.Text.EncodingProvider> per rendere disponibili le codifiche della tabella codici alle app destinate al piattaforma UWP (Universal Windows Platform).</span><span class="sxs-lookup"><span data-stu-id="46fae-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="46fae-120">API private</span><span class="sxs-lookup"><span data-stu-id="46fae-120">Private APIs</span></span>  

<span data-ttu-id="46fae-121">Queste API supportano l'infrastruttura del prodotto e non sono progettate/supportate per l'uso direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="46fae-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="46fae-122">Proprietà Microsoft. SqlServer. Server. SmiOrderProperty. Item</span><span class="sxs-lookup"><span data-stu-id="46fae-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="46fae-123">System. Exception. PrepForRemoting, metodo</span><span class="sxs-lookup"><span data-stu-id="46fae-123">System.Exception.PrepForRemoting Method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="46fae-124">Proprietà System. Data. SqlTypes. SqlChars. Stream</span><span class="sxs-lookup"><span data-stu-id="46fae-124">System.Data.SqlTypes.SqlChars.Stream Property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="46fae-125">System. Data. SqlTypes. SqlStreamChars (costruttore)</span><span class="sxs-lookup"><span data-stu-id="46fae-125">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="46fae-126">Proprietà System. Data. SqlTypes. SqlStreamChars. CanSeek</span><span class="sxs-lookup"><span data-stu-id="46fae-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="46fae-127">Proprietà System. Data. SqlTypes. SqlStreamChars. IsNull</span><span class="sxs-lookup"><span data-stu-id="46fae-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="46fae-128">Proprietà System. Data. SqlTypes. SqlStreamChars. length</span><span class="sxs-lookup"><span data-stu-id="46fae-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="46fae-129">System. Data. SqlTypes. SqlStreamChars. Close (metodo)</span><span class="sxs-lookup"><span data-stu-id="46fae-129">System.Data.SqlTypes.SqlStreamChars.Close Method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="46fae-130">System. Data. SqlTypes. SqlStreamChars. Dispose (metodo)</span><span class="sxs-lookup"><span data-stu-id="46fae-130">System.Data.SqlTypes.SqlStreamChars.Dispose Method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="46fae-131">Metodo System. Data. SqlTypes. SqlStreamChars. Flush</span><span class="sxs-lookup"><span data-stu-id="46fae-131">System.Data.SqlTypes.SqlStreamChars.Flush Method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="46fae-132">Metodo System. Data. SqlTypes. SqlStreamChars. Read</span><span class="sxs-lookup"><span data-stu-id="46fae-132">System.Data.SqlTypes.SqlStreamChars.Read Method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="46fae-133">Metodo System. Data. SqlTypes. SqlStreamChars. Seek</span><span class="sxs-lookup"><span data-stu-id="46fae-133">System.Data.SqlTypes.SqlStreamChars.Seek Method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="46fae-134">Metodo System. Data. SqlTypes. SqlStreamChars. selength</span><span class="sxs-lookup"><span data-stu-id="46fae-134">System.Data.SqlTypes.SqlStreamChars.SetLength Method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="46fae-135">Metodo System. Data. SqlTypes. SqlStreamChars. Write</span><span class="sxs-lookup"><span data-stu-id="46fae-135">System.Data.SqlTypes.SqlStreamChars.Write Method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="46fae-136">System. IO. MemoryStream. InternalGetOriginAndLength, metodo</span><span class="sxs-lookup"><span data-stu-id="46fae-136">System.IO.MemoryStream.InternalGetOriginAndLength Method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="46fae-137">Classe System .NET. Connection</span><span class="sxs-lookup"><span data-stu-id="46fae-137">System.Net.Connection Class</span></span>](connection.md)
* [<span data-ttu-id="46fae-138">System .NET. Connection. m\_campo di writeback</span><span class="sxs-lookup"><span data-stu-id="46fae-138">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md)
* [<span data-ttu-id="46fae-139">Classe System .NET. ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="46fae-139">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md)
* [<span data-ttu-id="46fae-140">Campo System .NET. ConnectionGroup. m\_ConnectionName</span><span class="sxs-lookup"><span data-stu-id="46fae-140">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="46fae-141">Proprietà System .NET. ConnectStream. Connection</span><span class="sxs-lookup"><span data-stu-id="46fae-141">System.Net.ConnectStream.Connection Property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="46fae-142">Classe System .NET. CoreResponseData</span><span class="sxs-lookup"><span data-stu-id="46fae-142">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="46fae-143">System .NET. CoreResponseData. m\_campo ResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="46fae-143">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="46fae-144">Campo System .NET. CoreResponseData. m\_StatusCode</span><span class="sxs-lookup"><span data-stu-id="46fae-144">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="46fae-145">System .NET. HttpWebRequest.\_campo autodirects</span><span class="sxs-lookup"><span data-stu-id="46fae-145">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md)
* [<span data-ttu-id="46fae-146">Campo System .NET. HttpWebRequest.\_CoreResponse</span><span class="sxs-lookup"><span data-stu-id="46fae-146">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="46fae-147">Campo System .NET. HttpWebRequest.\_HttpResponse</span><span class="sxs-lookup"><span data-stu-id="46fae-147">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md)
* [<span data-ttu-id="46fae-148">Proprietà System .NET. PooledStream. NetworkStream</span><span class="sxs-lookup"><span data-stu-id="46fae-148">System.Net.PooledStream.NetworkStream Property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="46fae-149">Classe System .NET. RtcState</span><span class="sxs-lookup"><span data-stu-id="46fae-149">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="46fae-150">Campo System .NET. ServicePoint. m\_ConnectionGroupList</span><span class="sxs-lookup"><span data-stu-id="46fae-150">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="46fae-151">Campo ServicePointTable di System .NET. ServicePointManager. s\_</span><span class="sxs-lookup"><span data-stu-id="46fae-151">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="46fae-152">Campo System .NET. TlsStream. m_Worker</span><span class="sxs-lookup"><span data-stu-id="46fae-152">System.Net.TlsStream.m_Worker Field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="46fae-153">Proprietà System .NET. Security. SslState. SslProtocol</span><span class="sxs-lookup"><span data-stu-id="46fae-153">System.Net.Security.SslState.SslProtocol Property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="46fae-154">Metodo System. ServiceModel. Channels. Message. BodyToString</span><span class="sxs-lookup"><span data-stu-id="46fae-154">System.ServiceModel.Channels.Message.BodyToString Method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="46fae-155">Metodo System. ServiceModel. Channels. Message. WriteStartHeaders</span><span class="sxs-lookup"><span data-stu-id="46fae-155">System.ServiceModel.Channels.Message.WriteStartHeaders Method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="46fae-156">System. Windows. Diagnostics. VisualDiagnostics. s\_campo isDebuggerCheckDisabledForTestPurposes</span><span class="sxs-lookup"><span data-stu-id="46fae-156">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="46fae-157">Classe System. Windows. Forms. Design. DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="46fae-157">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="46fae-158">Classe System. Windows. Forms. Design. DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="46fae-158">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="46fae-159">System. XML. XmlReader. CreateSqlReader, metodo</span><span class="sxs-lookup"><span data-stu-id="46fae-159">System.Xml.XmlReader.CreateSqlReader Method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="46fae-160">oggetto ADODB. Interfaccia di connessione</span><span class="sxs-lookup"><span data-stu-id="46fae-160">adodb.Connection Interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="46fae-161">oggetto ADODB. Enumerazione EventReason</span><span class="sxs-lookup"><span data-stu-id="46fae-161">adodb.EventReason Enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="46fae-162">oggetto ADODB. Enumerazione EventStatus</span><span class="sxs-lookup"><span data-stu-id="46fae-162">adodb.EventStatus Enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="46fae-163">stdole. Struttura DISPPARAMS</span><span class="sxs-lookup"><span data-stu-id="46fae-163">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="46fae-164">stdole. Struttura EXCEPINFO</span><span class="sxs-lookup"><span data-stu-id="46fae-164">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="46fae-165">stdole. Proprietà IFont.Name</span><span class="sxs-lookup"><span data-stu-id="46fae-165">stdole.IFont.Name Property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="46fae-166">stdole. Interfaccia IFontDisp</span><span class="sxs-lookup"><span data-stu-id="46fae-166">stdole.IFontDisp Interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="46fae-167">stdole. Proprietà IPicture. handle</span><span class="sxs-lookup"><span data-stu-id="46fae-167">stdole.IPicture.Handle Property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="46fae-168">stdole. Proprietà IPictureDisp. handle</span><span class="sxs-lookup"><span data-stu-id="46fae-168">stdole.IPictureDisp.Handle Property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="46fae-169">stdole. Interfaccia StdFont</span><span class="sxs-lookup"><span data-stu-id="46fae-169">stdole.StdFont Interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="46fae-170">stdole. Interfaccia StdPicture</span><span class="sxs-lookup"><span data-stu-id="46fae-170">stdole.StdPicture Interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="46fae-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46fae-171">See also</span></span>

* [<span data-ttu-id="46fae-172">.NET Framework e rilascio fuori programma</span><span class="sxs-lookup"><span data-stu-id="46fae-172">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
