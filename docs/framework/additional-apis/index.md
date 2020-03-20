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
# <a name="additional-class-libraries-and-apis"></a>Librerie di classi e API aggiuntive

.NET Framework è in continua evoluzione. Per migliorare lo sviluppo multipiattaforma e introdurre nuove funzionalità in anticipo, nuove funzionalità vengono rilasciate fuori banda (OOB). Questo argomento elenca i progetti fuori banda (OOB) per i quali viene fornita la documentazione.  
  
Inoltre, alcune librerie sono destinate a piattaforme o implementazioni specifiche di .NET Framework. Ad esempio, <xref:System.Text.CodePagesEncodingProvider> la classe rende le codifiche della tabella codici disponibili per le app UWP sviluppate con .NET Framework. Questo argomento include anche un elenco di queste librerie.  
  
## <a name="oob-projects"></a>Progetti OOB
  
| Project | Descrizione |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Fornisce raccolte thread-safe e che non modificano mai il contenuto. |
| <xref:System.Net.Http.WinHttpHandler> | Fornisce un gestore di messaggi per <xref:System.Net.Http.HttpClient> basato sull'interfaccia WinHTTP di Windows. |
| <xref:System.Numerics> | Fornisce una libreria di tipi di vettori in grado di sfruttare l'accelerazione basata su hardware SIMD.|
| <xref:System.Threading.Tasks.Dataflow> | La libreria del flusso di dati TPL fornisce i componenti del flusso di dati per aumentare l'affidabilità delle applicazioni abilitate per la concorrenza. |  

## <a name="platform-specific-libraries"></a>Librerie specifiche della piattaforma
  
| Project | Descrizione |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Estende <xref:System.Text.EncodingProvider> la classe per rendere le codifiche della tabella codici disponibili per le app destinate alla piattaforma Windows universale. |  
  
## <a name="private-apis"></a>API private  

Queste API supportano l'infrastruttura del prodotto e non sono progettate/supportate per l'uso direttamente dal codice.  
  
* [Microsoft.SqlServer.Server.SmiOrderProperty.Item Proprietà](microsoft.sqlserver.server.smiorderproperty.item.md)
* [Metodo System.Exception.PrepForRemoting](system.exception.prepforremoting.md)
* [Proprietà System.Data.SqlTypes.SqlChars.Stream](system.data.sqltypes.sqlchars.stream.md)
* [Costruttore System.Data.SqlTypes.SqlStreamChars](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [Proprietà System.Data.SqlTypes.SqlStreamChars.CanSeek](system.data.sqltypes.sqlstreamchars.canseek.md)
* [Proprietà System.Data.SqlTypes.SqlStreamChars.IsNull](system.data.sqltypes.sqlstreamchars.isnull.md)
* [Proprietà System.Data.SqlTypes.SqlStreamChars.Length](system.data.sqltypes.sqlstreamchars.length.md)
* [Metodo System.Data.SqlTypes.SqlStreamChars.Close](system.data.sqltypes.sqlstreamchars.close.md)
* [Metodo System.Data.SqlTypes.SqlStreamChars.Dispose](system.data.sqltypes.sqlstreamchars.dispose.md)
* [Metodo System.Data.SqlTypes.SqlStreamChars.Flush](system.data.sqltypes.sqlstreamchars.flush.md)
* [Metodo System.Data.SqlTypes.SqlStreamChars.Read](system.data.sqltypes.sqlstreamchars.read.md)
* [Metodo System.Data.SqlTypes.SqlStreamChars.Seek](system.data.sqltypes.sqlstreamchars.seek.md)
* [Metodo System.Data.SqlTypes.SqlStreamChars.SetLength](system.data.sqltypes.sqlstreamchars.setlength.md)
* [Metodo System.Data.SqlTypes.SqlStreamChars.Write](system.data.sqltypes.sqlstreamchars.write.md)
* [Metodo System.IO.MemoryStream.InternalGetOriginAndLength](system.io.memorystream.internalgetoriginandlength.md)
* [Classe System.Net.Connection](connection.md)
* [Campo WriteList System.Net.Connection.m\_](m_writelist.md)
* [Classe System.Net.ConnectionGroup](connectiongroup.md)
* [System.Net.ConnectionGroup.m\_Campo ConnectionList](m_connectionlist.md)
* [Proprietà System.Net.ConnectStream.Connection](system.net.connectstream.connection.md)
* [Classe System.Net.CoreResponseData](coreresponsedata.md)
* [System.Net.CoreResponseData.m\_ResponseHeaders Campo](coreresponsedata_m_responseheaders.md)
* [System.Net.CoreResponseData.m\_Campo StatusCode](coreresponsedata_m_statuscode.md)
* [System.Net.HttpWebRequest. \_AutoRedirects Campo](_autoredirects.md)
* [System.Net.HttpWebRequest. \_Campo CoreResponse](httpwebrequest__coreresponse.md)
* [System.Net.HttpWebRequest. \_HttpResponse Campo](_httpresponse.md)
* [Proprietà System.Net.PooledStream.NetworkStream](system.net.pooledstream.networkstream.md)
* [Classe System.Net.RtcState](system.net.rtcstate.md)
* [System.Net.ServicePoint.m\_ConnectionGroupList Campo](m_connectiongrouplist.md)
* [Campo ServicePointTable di System.Net.ServicePointManager.s\_](s_servicepointtable.md)
* [Campo System.Net.TlsStream.m_Worker](system.net.tlsstream.m_worker.md)
* [Proprietà System.Net.Security.SslState.SslProtocol](system.net.security.sslstate.sslprotocol.md)
* [Metodo System.ServiceModel.Channels.Message.BodyToString](system.servicemodel.channels.message.bodytostring.md)
* [Metodo System.ServiceModel.Channels.Message.WriteStartHeaders](system.servicemodel.channels.message.writestartheaders.md)
* [System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Campo](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [Classe System.Windows.Forms.Design.DataMemberFieldEditor](datamemberfieldeditor-class.md)
* [Classe System.Windows.Forms.Design.DataMemberListEditor](datamemberlisteditor-class.md)
* [Metodo System.Xml.XmlReader.CreateSqlReader](system.xml.xmlreader.createsqlreader.md)
* [Adodb. Interfaccia di connessione](adodb.connection.md)
* [Adodb. Enumerazione EventReason](adodb.eventreasonenum.md)
* [Adodb. Enumerazione EventStatus](adodb.eventstatusenum.md)
* [stdole. Struttura DISPPARAMS](stdole.dispparams.md)
* [stdole. ExCEPINFO Struttura](stdole.excepinfo.md)
* [stdole. IFont.Name Proprietà](stdole.ifont.name.md)
* [stdole. Interfaccia IFontDisp](stdole.ifontdisp.md)
* [stdole. IPicture.Handle Proprietà](stdole.ipicture.handle.md)
* [stdole. IPictureDisp.Handle Proprietà](stdole.ipicturedisp.handle.md)
* [stdole. Interfaccia StdFont](stdole.stdfont.md)
* [stdole. Interfaccia StdPicture](stdole.stdpicture.md)
  
## <a name="see-also"></a>Vedere anche

* [.NET Framework e rilascio fuori programma](../get-started/the-net-framework-and-out-of-band-releases.md)
