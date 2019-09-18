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
ms.topic: conceptual
ms.openlocfilehash: 0aed6f32bbd3ffdc9446e9d17be2d90c62444ee1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053248"
---
# <a name="additional-class-libraries-and-apis"></a>Librerie di classi e API aggiuntive

Il .NET Framework è in continua evoluzione. Per migliorare lo sviluppo multipiattaforma e introdurre nuove funzionalità in anticipo, le nuove funzionalità vengono rilasciate fuori banda (OOB). Questo argomento elenca i progetti fuori banda (OOB) per i quali viene fornita la documentazione.  
  
Inoltre, alcune librerie sono destinate a piattaforme o implementazioni specifiche di .NET Framework. Ad esempio, la <xref:System.Text.CodePagesEncodingProvider> classe rende disponibili le codifiche della tabella codici per le app UWP sviluppate usando il .NET Framework. Questo argomento include anche un elenco di queste librerie.  
  
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
| <xref:System.Text.CodePagesEncodingProvider> | Estende la <xref:System.Text.EncodingProvider> classe per rendere disponibili le codifiche della tabella codici alle app destinate al piattaforma UWP (Universal Windows Platform). |  
  
## <a name="private-apis"></a>API private  

Queste API supportano l'infrastruttura del prodotto e non sono progettate/supportate per l'uso direttamente dal codice.  
  
| Nome dell'API |
| -------- |
| [Classe System .NET. Connection](connection.md) |
| [Campo di writeback di System .NET\_. Connection. m](m_writelist.md) |
| [Classe System .NET. ConnectionGroup](connectiongroup.md) |
| [System.Net.ConnectionGroup.m\_ConnectionList Field](m_connectionlist.md) |
| [Classe System .NET. CoreResponseData](coreresponsedata.md) |
| [System.Net.CoreResponseData.m\_ResponseHeaders Field](coreresponsedata_m_responseheaders.md) |
| [System.Net.CoreResponseData.m\_StatusCode Field](coreresponsedata_m_statuscode.md) |
| [System .NET. HttpWebRequest. \_Campo autodirects](_autoredirects.md) |
| [System .NET. HttpWebRequest. \_Campo CoreResponse](httpwebrequest__coreresponse.md) |
| [System .NET. HttpWebRequest. \_Campo HttpResponse](_httpresponse.md) |
| [System.Net.ServicePoint.m\_ConnectionGroupList Field](m_connectiongrouplist.md) |
| [System.Net.ServicePointManager.s\_ServicePointTable Field](s_servicepointtable.md) |
| [System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field](s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [Classe System. Windows. Forms. Design. DataMemberFieldEditor](datamemberfieldeditor-class.md) |
| [Classe System. Windows. Forms. Design. DataMemberListEditor](datamemberlisteditor-class.md) |
  
## <a name="see-also"></a>Vedere anche

- [.NET Framework e rilascio fuori programma](../get-started/the-net-framework-and-out-of-band-releases.md)
