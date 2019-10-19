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
ms.openlocfilehash: 809ac026244b24aee69ec0d6c40c10a1248c234c
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579107"
---
# <a name="additional-class-libraries-and-apis"></a>Librerie di classi e API aggiuntive

Il .NET Framework è in continua evoluzione. Per migliorare lo sviluppo multipiattaforma e introdurre nuove funzionalità in anticipo, le nuove funzionalità vengono rilasciate fuori banda (OOB). Questo argomento elenca i progetti fuori banda (OOB) per i quali viene fornita la documentazione.  
  
Inoltre, alcune librerie sono destinate a piattaforme o implementazioni specifiche di .NET Framework. Ad esempio, la classe <xref:System.Text.CodePagesEncodingProvider> rende disponibili le codifiche della tabella codici per le app UWP sviluppate usando il .NET Framework. Questo argomento include anche un elenco di queste librerie.  
  
## <a name="oob-projects"></a>Progetti OOB
  
| Progetto | Descrizione |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Fornisce raccolte thread-safe e che non modificano mai il contenuto. |
| <xref:System.Net.Http.WinHttpHandler> | Fornisce un gestore di messaggi per <xref:System.Net.Http.HttpClient> basato sull'interfaccia WinHTTP di Windows. |
| <xref:System.Numerics> | Fornisce una libreria di tipi di vettori in grado di sfruttare l'accelerazione basata su hardware SIMD.| 
| <xref:System.Threading.Tasks.Dataflow> | La libreria del flusso di dati TPL fornisce i componenti del flusso di dati per aumentare l'affidabilità delle applicazioni abilitate per la concorrenza. |  

## <a name="platform-specific-libraries"></a>Librerie specifiche della piattaforma
  
| Progetto | Descrizione |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Estende la classe <xref:System.Text.EncodingProvider> per rendere disponibili le codifiche della tabella codici per le app destinate al piattaforma UWP (Universal Windows Platform). |  
  
## <a name="private-apis"></a>API private  

Queste API supportano l'infrastruttura del prodotto e non sono progettate/supportate per l'uso direttamente dal codice.  
  
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
* [Classe System .NET. Connection](connection.md)
* [Campo System .NET. Connection. m \_WriteList](m_writelist.md)
* [Classe System .NET. ConnectionGroup](connectiongroup.md)
* [Campo di \_ConnectionList System .NET. ConnectionGroup. m](m_connectionlist.md)
* [Classe System .NET. CoreResponseData](coreresponsedata.md)
* [Campo di \_ResponseHeaders System .NET. CoreResponseData. m](coreresponsedata_m_responseheaders.md)
* [Campo di \_StatusCode System .NET. CoreResponseData. m](coreresponsedata_m_statuscode.md)
* [System .NET. HttpWebRequest. \_AutoRedirects campo](_autoredirects.md)
* [System .NET. HttpWebRequest. \_CoreResponse campo](httpwebrequest__coreresponse.md)
* [System .NET. HttpWebRequest. \_HttpResponse campo](_httpresponse.md)
* [Campo di \_ConnectionGroupList System .NET. ServicePoint. m](m_connectiongrouplist.md)
* [Campo \_ServicePointTable di System .NET. ServicePointManager. s](s_servicepointtable.md)
* [Campo di \_isDebuggerCheckDisabledForTestPurposes System. Windows. Diagnostics. VisualDiagnostics. s](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [Classe System. Windows. Forms. Design. DataMemberFieldEditor](datamemberfieldeditor-class.md)
* [Classe System. Windows. Forms. Design. DataMemberListEditor](datamemberlisteditor-class.md)
* [System. XML. XmlReader. CreateSqlReader, metodo](system.xml.xmlreader.createsqlreader.md)
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

* [.NET Framework e rilascio fuori programma](../get-started/the-net-framework-and-out-of-band-releases.md)
