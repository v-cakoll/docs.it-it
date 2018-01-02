---
title: Librerie di classi e API aggiuntive
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c22de3ed401e0be10b155649395da43cedb35e6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="additional-class-libraries-and-apis"></a>Librerie di classi e API aggiuntive

Poiché .NET Framework è in costante evoluzione, vengono rilasciate nuove funzionalità fuori programma (OOB) per migliorare lo sviluppo multipiattaforma o introdurre nuove funzionalità in anteprima per i clienti. Questo argomento elenca i progetti fuori banda (OOB) per i quali viene fornita la documentazione.  
  
Inoltre, alcune librerie sono destinate a piattaforme o implementazioni specifiche di .NET Framework. Ad esempio, il <xref:System.Text.CodePagesEncodingProvider> rende codifiche delle tabelle codici di codice disponibili per App UWP sviluppata con .NET Framework. Questo argomento include anche un elenco di queste librerie.  
  
## <a name="oob-projects"></a>Progetti OOB
  
| Progetto | Descrizione |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Fornisce raccolte thread-safe e che non modificano mai il contenuto. |
| <xref:System.Net.Http.WinHttpHandler> | Fornisce un gestore di messaggi per <xref:System.Net.Http.HttpClient> basato sull'interfaccia WinHTTP di Windows. |
| [System.Numerics.Vectors](https://msdn.microsoft.com/library/mt452176.aspx) | Fornisce una libreria di tipi di vettori in grado di sfruttare l'accelerazione basata su hardware SIMD.| 
| <xref:System.Threading.Tasks.Dataflow> | La libreria del flusso di dati TPL fornisce i componenti del flusso di dati per aumentare l'affidabilità delle applicazioni abilitate per la concorrenza. |  

## <a name="platform-specific-libraries"></a>Librerie specifiche della piattaforma
  
| Progetto | Descrizione |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Estende la <xref:System.Text.EncodingProvider> classe per rendere disponibili per le applicazioni che usano la piattaforma Windows universale codifiche delle tabelle codici di codice. |  
  
## <a name="private-apis"></a>API private  

Queste API supportano l'infrastruttura del prodotto e non sono progettate/supportate per l'uso direttamente dal codice.  
  
| Nome dell'API |
| -------- |
| [Classe System.Net.Connection](../../../docs/framework/additional-apis/connection.md) |
| [System.Net.Connection.m\_WriteList campo](../../../docs/framework/additional-apis/m_writelist.md) |
| [Classe System.Net.ConnectionGroup](../../../docs/framework/additional-apis/connectiongroup.md) |
| [System.Net.ConnectionGroup.m\_ConnectionList campo](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [System.NET. HttpWebRequest. \_HttpResponse campo](../../../docs/framework/additional-apis/_httpresponse.md) |
| [System.NET. HttpWebRequest. \_AutoRedirects campo](../../../docs/framework/additional-apis/_autoredirects.md) |
| [System.Net.ServicePoint.m\_ConnectionGroupList campo](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [System.Net.ServicePointManager.s\_ServicePointTable campo](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes campo](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [Classe System.Windows.Forms.Design.DataMemberFieldEditor](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [Classe System.Windows.Forms.Design.DataMemberListEditor](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a>Vedere anche

[.NET Framework e rilascio fuori programma](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
