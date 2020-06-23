---
title: Librerie di classi e API aggiuntive
description: Esplora librerie di classi e API aggiuntive in .NET, inclusi i progetti fuori banda (OOB), le librerie specifiche della piattaforma e le API private.
ms.date: 06/12/2020
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: 0b888d2f0e80685ba993682b2f3067cf8aee15bc
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989734"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="75359-103">Librerie di classi e API aggiuntive</span><span class="sxs-lookup"><span data-stu-id="75359-103">Additional class libraries and APIs</span></span>

<span data-ttu-id="75359-104">Questo articolo elenca .NET Framework API rilasciate fuori banda, destinate a una piattaforma specifica o sono tipi privati o interni.</span><span class="sxs-lookup"><span data-stu-id="75359-104">This article lists .NET Framework APIs that either were released out of band, target a specific platform, or are private or internal types.</span></span>

## <a name="oob-projects"></a><span data-ttu-id="75359-105">Progetti OOB</span><span class="sxs-lookup"><span data-stu-id="75359-105">OOB projects</span></span>

<span data-ttu-id="75359-106">Per migliorare lo sviluppo multipiattaforma e introdurre presto nuove funzionalità, alcune .NET Framework funzionalità sono state rilasciate fuori banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="75359-106">To improve cross-platform development and introduce new functionality early, some .NET Framework features were released out of band (OOB).</span></span>

| <span data-ttu-id="75359-107">Project</span><span class="sxs-lookup"><span data-stu-id="75359-107">Project</span></span> | <span data-ttu-id="75359-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75359-108">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="75359-109">Fornisce raccolte thread-safe e che non modificano mai il contenuto.</span><span class="sxs-lookup"><span data-stu-id="75359-109">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="75359-110">Fornisce un gestore di messaggi per <xref:System.Net.Http.HttpClient> basato sull'interfaccia WinHTTP di Windows.</span><span class="sxs-lookup"><span data-stu-id="75359-110">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="75359-111">Fornisce una libreria di tipi di vettori in grado di sfruttare l'accelerazione basata su hardware SIMD.</span><span class="sxs-lookup"><span data-stu-id="75359-111">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>|
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="75359-112">La libreria del flusso di dati TPL fornisce i componenti del flusso di dati per aumentare l'affidabilità delle applicazioni abilitate per la concorrenza.</span><span class="sxs-lookup"><span data-stu-id="75359-112">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="75359-113">Librerie specifiche della piattaforma</span><span class="sxs-lookup"><span data-stu-id="75359-113">Platform-specific libraries</span></span>

<span data-ttu-id="75359-114">Alcune librerie sono destinate a piattaforme specifiche.</span><span class="sxs-lookup"><span data-stu-id="75359-114">Some libraries target specific platforms.</span></span> <span data-ttu-id="75359-115">Ad esempio, la <xref:System.Text.CodePagesEncodingProvider> classe rende disponibili le codifiche della tabella codici per le app UWP sviluppate con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="75359-115">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using .NET Framework.</span></span>
  
| <span data-ttu-id="75359-116">Project</span><span class="sxs-lookup"><span data-stu-id="75359-116">Project</span></span> | <span data-ttu-id="75359-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75359-117">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="75359-118">Estende la <xref:System.Text.EncodingProvider> classe per rendere disponibili le codifiche della tabella codici alle app destinate al piattaforma UWP (Universal Windows Platform).</span><span class="sxs-lookup"><span data-stu-id="75359-118">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="75359-119">API private</span><span class="sxs-lookup"><span data-stu-id="75359-119">Private APIs</span></span>  

<span data-ttu-id="75359-120">Queste API supportano l'infrastruttura del prodotto e non sono progettate o supportate per l'uso diretto dal codice.</span><span class="sxs-lookup"><span data-stu-id="75359-120">These APIs support the product infrastructure and are not intended or supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="75359-121">Proprietà Microsoft. SqlServer. Server. SmiOrderProperty. Item</span><span class="sxs-lookup"><span data-stu-id="75359-121">Microsoft.SqlServer.Server.SmiOrderProperty.Item property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="75359-122">System. Exception. PrepForRemoting, metodo</span><span class="sxs-lookup"><span data-stu-id="75359-122">System.Exception.PrepForRemoting method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="75359-123">Proprietà System. Data. SqlTypes. SqlChars. Stream</span><span class="sxs-lookup"><span data-stu-id="75359-123">System.Data.SqlTypes.SqlChars.Stream property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="75359-124">System. Data. SqlTypes. SqlStreamChars (costruttore)</span><span class="sxs-lookup"><span data-stu-id="75359-124">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="75359-125">Proprietà System. Data. SqlTypes. SqlStreamChars. CanSeek</span><span class="sxs-lookup"><span data-stu-id="75359-125">System.Data.SqlTypes.SqlStreamChars.CanSeek property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="75359-126">Proprietà System. Data. SqlTypes. SqlStreamChars. IsNull</span><span class="sxs-lookup"><span data-stu-id="75359-126">System.Data.SqlTypes.SqlStreamChars.IsNull property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="75359-127">Proprietà System. Data. SqlTypes. SqlStreamChars. length</span><span class="sxs-lookup"><span data-stu-id="75359-127">System.Data.SqlTypes.SqlStreamChars.Length property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="75359-128">System. Data. SqlTypes. SqlStreamChars. Close (metodo)</span><span class="sxs-lookup"><span data-stu-id="75359-128">System.Data.SqlTypes.SqlStreamChars.Close method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="75359-129">System. Data. SqlTypes. SqlStreamChars. Dispose (metodo)</span><span class="sxs-lookup"><span data-stu-id="75359-129">System.Data.SqlTypes.SqlStreamChars.Dispose method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="75359-130">Metodo System. Data. SqlTypes. SqlStreamChars. Flush</span><span class="sxs-lookup"><span data-stu-id="75359-130">System.Data.SqlTypes.SqlStreamChars.Flush method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="75359-131">Metodo System. Data. SqlTypes. SqlStreamChars. Read</span><span class="sxs-lookup"><span data-stu-id="75359-131">System.Data.SqlTypes.SqlStreamChars.Read method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="75359-132">Metodo System. Data. SqlTypes. SqlStreamChars. Seek</span><span class="sxs-lookup"><span data-stu-id="75359-132">System.Data.SqlTypes.SqlStreamChars.Seek method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="75359-133">Metodo System. Data. SqlTypes. SqlStreamChars. selength</span><span class="sxs-lookup"><span data-stu-id="75359-133">System.Data.SqlTypes.SqlStreamChars.SetLength method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="75359-134">Metodo System. Data. SqlTypes. SqlStreamChars. Write</span><span class="sxs-lookup"><span data-stu-id="75359-134">System.Data.SqlTypes.SqlStreamChars.Write method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="75359-135">System. IO. MemoryStream. InternalGetOriginAndLength, metodo</span><span class="sxs-lookup"><span data-stu-id="75359-135">System.IO.MemoryStream.InternalGetOriginAndLength method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="75359-136">System .NET. comnetos (classe)</span><span class="sxs-lookup"><span data-stu-id="75359-136">System.Net.ComNetOS class</span></span>](system.net.comnetos.md)
* [<span data-ttu-id="75359-137">Classe System .NET. Connection</span><span class="sxs-lookup"><span data-stu-id="75359-137">System.Net.Connection class</span></span>](connection.md)
* [<span data-ttu-id="75359-138">Campo di writeback di System .NET. Connection. m \_</span><span class="sxs-lookup"><span data-stu-id="75359-138">System.Net.Connection.m\_WriteList field</span></span>](m_writelist.md)
* [<span data-ttu-id="75359-139">Classe System .NET. ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="75359-139">System.Net.ConnectionGroup class</span></span>](connectiongroup.md)
* [<span data-ttu-id="75359-140">Campo di connessione di System .NET. ConnectionGroup. m \_</span><span class="sxs-lookup"><span data-stu-id="75359-140">System.Net.ConnectionGroup.m\_ConnectionList field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="75359-141">Proprietà System .NET. ConnectStream. Connection</span><span class="sxs-lookup"><span data-stu-id="75359-141">System.Net.ConnectStream.Connection property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="75359-142">Classe System .NET. CoreResponseData</span><span class="sxs-lookup"><span data-stu-id="75359-142">System.Net.CoreResponseData class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="75359-143">Campo System .NET. CoreResponseData. m \_ ResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="75359-143">System.Net.CoreResponseData.m\_ResponseHeaders field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="75359-144">Campo di System .NET. CoreResponseData. m \_ statusCode</span><span class="sxs-lookup"><span data-stu-id="75359-144">System.Net.CoreResponseData.m\_StatusCode field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="75359-145">Classe System .NET. ExceptionHelper</span><span class="sxs-lookup"><span data-stu-id="75359-145">System.Net.ExceptionHelper class</span></span>](system.net.exceptionhelper.md)
* [<span data-ttu-id="75359-146">Classe System .NET. HttpStatusDescription</span><span class="sxs-lookup"><span data-stu-id="75359-146">System.Net.HttpStatusDescription class</span></span>](system.net.httpstatusdescription.md)
* [<span data-ttu-id="75359-147">System .NET. HttpWebRequest. \_ Campo autodirects</span><span class="sxs-lookup"><span data-stu-id="75359-147">System.Net.HttpWebRequest.\_AutoRedirects field</span></span>](_autoredirects.md)
* [<span data-ttu-id="75359-148">System .NET. HttpWebRequest. \_ Campo CoreResponse</span><span class="sxs-lookup"><span data-stu-id="75359-148">System.Net.HttpWebRequest.\_CoreResponse field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="75359-149">System .NET. HttpWebRequest. \_ Campo HttpResponse</span><span class="sxs-lookup"><span data-stu-id="75359-149">System.Net.HttpWebRequest.\_HttpResponse field</span></span>](_httpresponse.md)
* [<span data-ttu-id="75359-150">Classe System .NET. Logging</span><span class="sxs-lookup"><span data-stu-id="75359-150">System.Net.Logging class</span></span>](system.net.logging.md)
* [<span data-ttu-id="75359-151">Classe System .NET. mail. MailAddressParser</span><span class="sxs-lookup"><span data-stu-id="75359-151">System.Net.Mail.MailAddressParser class</span></span>](system.net.mail.mailaddressparser.md)
* [<span data-ttu-id="75359-152">Classe System .NET. mail. QuotedPairReader</span><span class="sxs-lookup"><span data-stu-id="75359-152">System.Net.Mail.QuotedPairReader class</span></span>](system.net.mail.quotedpairreader.md)
* [<span data-ttu-id="75359-153">Classe System .NET. MIME. MailBnfHelper</span><span class="sxs-lookup"><span data-stu-id="75359-153">System.Net.Mime.MailBnfHelper class</span></span>](system.net.mime.mailbnfhelper.md)
* [<span data-ttu-id="75359-154">Proprietà System .NET. PooledStream. NetworkStream</span><span class="sxs-lookup"><span data-stu-id="75359-154">System.Net.PooledStream.NetworkStream property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="75359-155">Classe System .NET. RtcState</span><span class="sxs-lookup"><span data-stu-id="75359-155">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="75359-156">Proprietà System .NET. Security. SslState. SslProtocol</span><span class="sxs-lookup"><span data-stu-id="75359-156">System.Net.Security.SslState.SslProtocol property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="75359-157">Campo System .NET. ServicePoint. m \_ ConnectionGroupList</span><span class="sxs-lookup"><span data-stu-id="75359-157">System.Net.ServicePoint.m\_ConnectionGroupList field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="75359-158">System .NET. ServicePointManager. CloseConnectionGroups, metodo</span><span class="sxs-lookup"><span data-stu-id="75359-158">System.Net.ServicePointManager.CloseConnectionGroups method</span></span>](system.net.servicepointmanager.closeconnectiongroups.md)
* [<span data-ttu-id="75359-159">Campo System .NET. ServicePointManager. s \_ ServicePointTable</span><span class="sxs-lookup"><span data-stu-id="75359-159">System.Net.ServicePointManager.s\_ServicePointTable field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="75359-160">Campo System .NET. TlsStream. m_Worker</span><span class="sxs-lookup"><span data-stu-id="75359-160">System.Net.TlsStream.m_Worker field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="75359-161">Classe System .NET. UnsafeNclNativeMethods</span><span class="sxs-lookup"><span data-stu-id="75359-161">System.Net.UnsafeNclNativeMethods class</span></span>](system.net.unsafenclnativemethods.md)
* [<span data-ttu-id="75359-162">System .NET. WebHeaderCollection. AddInternal, metodo</span><span class="sxs-lookup"><span data-stu-id="75359-162">System.Net.WebHeaderCollection.AddInternal method</span></span>](system.net.webheadercollection.addinternal.md)
* [<span data-ttu-id="75359-163">Metodo System. ServiceModel. Channels. Message. BodyToString</span><span class="sxs-lookup"><span data-stu-id="75359-163">System.ServiceModel.Channels.Message.BodyToString method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="75359-164">Metodo System. ServiceModel. Channels. Message. WriteStartHeaders</span><span class="sxs-lookup"><span data-stu-id="75359-164">System.ServiceModel.Channels.Message.WriteStartHeaders method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="75359-165">Campo System. Windows. Diagnostics. VisualDiagnostics. s \_ isDebuggerCheckDisabledForTestPurposes</span><span class="sxs-lookup"><span data-stu-id="75359-165">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="75359-166">Classe System. Windows. Forms. Design. DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="75359-166">System.Windows.Forms.Design.DataMemberFieldEditor class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="75359-167">Classe System. Windows. Forms. Design. DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="75359-167">System.Windows.Forms.Design.DataMemberListEditor class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="75359-168">System.Xml.Xmlmetodo Reader. CreateSqlReader</span><span class="sxs-lookup"><span data-stu-id="75359-168">System.Xml.XmlReader.CreateSqlReader method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="75359-169">oggetto ADODB. Interfaccia di connessione</span><span class="sxs-lookup"><span data-stu-id="75359-169">adodb.Connection interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="75359-170">oggetto ADODB. Enumerazione EventReason</span><span class="sxs-lookup"><span data-stu-id="75359-170">adodb.EventReason enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="75359-171">oggetto ADODB. Enumerazione EventStatus</span><span class="sxs-lookup"><span data-stu-id="75359-171">adodb.EventStatus enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="75359-172">stdole. Struttura DISPPARAMS</span><span class="sxs-lookup"><span data-stu-id="75359-172">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="75359-173">stdole. Struttura EXCEPINFO</span><span class="sxs-lookup"><span data-stu-id="75359-173">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="75359-174">stdole. Proprietà IFont.Name</span><span class="sxs-lookup"><span data-stu-id="75359-174">stdole.IFont.Name property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="75359-175">stdole. Interfaccia IFontDisp</span><span class="sxs-lookup"><span data-stu-id="75359-175">stdole.IFontDisp interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="75359-176">stdole. Proprietà IPicture. handle</span><span class="sxs-lookup"><span data-stu-id="75359-176">stdole.IPicture.Handle property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="75359-177">stdole. Proprietà IPictureDisp. handle</span><span class="sxs-lookup"><span data-stu-id="75359-177">stdole.IPictureDisp.Handle property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="75359-178">stdole. Interfaccia StdFont</span><span class="sxs-lookup"><span data-stu-id="75359-178">stdole.StdFont interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="75359-179">stdole. Interfaccia StdPicture</span><span class="sxs-lookup"><span data-stu-id="75359-179">stdole.StdPicture interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="75359-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75359-180">See also</span></span>

* [<span data-ttu-id="75359-181">.NET Framework e versioni fuori banda</span><span class="sxs-lookup"><span data-stu-id="75359-181">.NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
