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
# <a name="additional-class-libraries-and-apis"></a>Librerie di classi e API aggiuntive

Questo articolo elenca .NET Framework API rilasciate fuori banda, destinate a una piattaforma specifica o sono tipi privati o interni.

## <a name="oob-projects"></a>Progetti OOB

Per migliorare lo sviluppo multipiattaforma e introdurre presto nuove funzionalità, alcune .NET Framework funzionalità sono state rilasciate fuori banda (OOB).

| Project | Descrizione |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Fornisce raccolte thread-safe e che non modificano mai il contenuto. |
| <xref:System.Net.Http.WinHttpHandler> | Fornisce un gestore di messaggi per <xref:System.Net.Http.HttpClient> basato sull'interfaccia WinHTTP di Windows. |
| <xref:System.Numerics> | Fornisce una libreria di tipi di vettori in grado di sfruttare l'accelerazione basata su hardware SIMD.|
| <xref:System.Threading.Tasks.Dataflow> | La libreria del flusso di dati TPL fornisce i componenti del flusso di dati per aumentare l'affidabilità delle applicazioni abilitate per la concorrenza. |  

## <a name="platform-specific-libraries"></a>Librerie specifiche della piattaforma

Alcune librerie sono destinate a piattaforme specifiche. Ad esempio, la <xref:System.Text.CodePagesEncodingProvider> classe rende disponibili le codifiche della tabella codici per le app UWP sviluppate con .NET Framework.
  
| Project | Descrizione |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Estende la <xref:System.Text.EncodingProvider> classe per rendere disponibili le codifiche della tabella codici alle app destinate al piattaforma UWP (Universal Windows Platform). |  
  
## <a name="private-apis"></a>API private  

Queste API supportano l'infrastruttura del prodotto e non sono progettate o supportate per l'uso diretto dal codice.  
  
* [Proprietà Microsoft. SqlServer. Server. SmiOrderProperty. Item](microsoft.sqlserver.server.smiorderproperty.item.md)
* [System. Exception. PrepForRemoting, metodo](system.exception.prepforremoting.md)
* [Proprietà System. Data. SqlTypes. SqlChars. Stream](system.data.sqltypes.sqlchars.stream.md)
* [System. Data. SqlTypes. SqlStreamChars (costruttore)](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [Proprietà System. Data. SqlTypes. SqlStreamChars. CanSeek](system.data.sqltypes.sqlstreamchars.canseek.md)
* [Proprietà System. Data. SqlTypes. SqlStreamChars. IsNull](system.data.sqltypes.sqlstreamchars.isnull.md)
* [Proprietà System. Data. SqlTypes. SqlStreamChars. length](system.data.sqltypes.sqlstreamchars.length.md)
* [System. Data. SqlTypes. SqlStreamChars. Close (metodo)](system.data.sqltypes.sqlstreamchars.close.md)
* [System. Data. SqlTypes. SqlStreamChars. Dispose (metodo)](system.data.sqltypes.sqlstreamchars.dispose.md)
* [Metodo System. Data. SqlTypes. SqlStreamChars. Flush](system.data.sqltypes.sqlstreamchars.flush.md)
* [Metodo System. Data. SqlTypes. SqlStreamChars. Read](system.data.sqltypes.sqlstreamchars.read.md)
* [Metodo System. Data. SqlTypes. SqlStreamChars. Seek](system.data.sqltypes.sqlstreamchars.seek.md)
* [Metodo System. Data. SqlTypes. SqlStreamChars. selength](system.data.sqltypes.sqlstreamchars.setlength.md)
* [Metodo System. Data. SqlTypes. SqlStreamChars. Write](system.data.sqltypes.sqlstreamchars.write.md)
* [System. IO. MemoryStream. InternalGetOriginAndLength, metodo](system.io.memorystream.internalgetoriginandlength.md)
* [System .NET. comnetos (classe)](system.net.comnetos.md)
* [Classe System .NET. Connection](connection.md)
* [Campo di writeback di System .NET. Connection. m \_](m_writelist.md)
* [Classe System .NET. ConnectionGroup](connectiongroup.md)
* [Campo di connessione di System .NET. ConnectionGroup. m \_](m_connectionlist.md)
* [Proprietà System .NET. ConnectStream. Connection](system.net.connectstream.connection.md)
* [Classe System .NET. CoreResponseData](coreresponsedata.md)
* [Campo System .NET. CoreResponseData. m \_ ResponseHeaders](coreresponsedata_m_responseheaders.md)
* [Campo di System .NET. CoreResponseData. m \_ statusCode](coreresponsedata_m_statuscode.md)
* [Classe System .NET. ExceptionHelper](system.net.exceptionhelper.md)
* [Classe System .NET. HttpStatusDescription](system.net.httpstatusdescription.md)
* [System .NET. HttpWebRequest. \_ Campo autodirects](_autoredirects.md)
* [System .NET. HttpWebRequest. \_ Campo CoreResponse](httpwebrequest__coreresponse.md)
* [System .NET. HttpWebRequest. \_ Campo HttpResponse](_httpresponse.md)
* [Classe System .NET. Logging](system.net.logging.md)
* [Classe System .NET. mail. MailAddressParser](system.net.mail.mailaddressparser.md)
* [Classe System .NET. mail. QuotedPairReader](system.net.mail.quotedpairreader.md)
* [Classe System .NET. MIME. MailBnfHelper](system.net.mime.mailbnfhelper.md)
* [Proprietà System .NET. PooledStream. NetworkStream](system.net.pooledstream.networkstream.md)
* [Classe System .NET. RtcState](system.net.rtcstate.md)
* [Proprietà System .NET. Security. SslState. SslProtocol](system.net.security.sslstate.sslprotocol.md)
* [Campo System .NET. ServicePoint. m \_ ConnectionGroupList](m_connectiongrouplist.md)
* [System .NET. ServicePointManager. CloseConnectionGroups, metodo](system.net.servicepointmanager.closeconnectiongroups.md)
* [Campo System .NET. ServicePointManager. s \_ ServicePointTable](s_servicepointtable.md)
* [Campo System .NET. TlsStream. m_Worker](system.net.tlsstream.m_worker.md)
* [Classe System .NET. UnsafeNclNativeMethods](system.net.unsafenclnativemethods.md)
* [System .NET. WebHeaderCollection. AddInternal, metodo](system.net.webheadercollection.addinternal.md)
* [Metodo System. ServiceModel. Channels. Message. BodyToString](system.servicemodel.channels.message.bodytostring.md)
* [Metodo System. ServiceModel. Channels. Message. WriteStartHeaders](system.servicemodel.channels.message.writestartheaders.md)
* [Campo System. Windows. Diagnostics. VisualDiagnostics. s \_ isDebuggerCheckDisabledForTestPurposes](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [Classe System. Windows. Forms. Design. DataMemberFieldEditor](datamemberfieldeditor-class.md)
* [Classe System. Windows. Forms. Design. DataMemberListEditor](datamemberlisteditor-class.md)
* [System.Xml.Xmlmetodo Reader. CreateSqlReader](system.xml.xmlreader.createsqlreader.md)
* [oggetto ADODB. Interfaccia di connessione](adodb.connection.md)
* [oggetto ADODB. Enumerazione EventReason](adodb.eventreasonenum.md)
* [oggetto ADODB. Enumerazione EventStatus](adodb.eventstatusenum.md)
* [stdole. Struttura DISPPARAMS](stdole.dispparams.md)
* [stdole. Struttura EXCEPINFO](stdole.excepinfo.md)
* [stdole. Proprietà IFont.Name](stdole.ifont.name.md)
* [stdole. Interfaccia IFontDisp](stdole.ifontdisp.md)
* [stdole. Proprietà IPicture. handle](stdole.ipicture.handle.md)
* [stdole. Proprietà IPictureDisp. handle](stdole.ipicturedisp.handle.md)
* [stdole. Interfaccia StdFont](stdole.stdfont.md)
* [stdole. Interfaccia StdPicture](stdole.stdpicture.md)
  
## <a name="see-also"></a>Vedere anche

* [.NET Framework e versioni fuori banda](../get-started/the-net-framework-and-out-of-band-releases.md)
