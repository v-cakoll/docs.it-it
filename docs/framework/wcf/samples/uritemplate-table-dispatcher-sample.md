---
title: Dispatcher di esempio nella tabella UriTemplate
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8fe3440c6c770052b40bbade7483e1c31e1671a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="uritemplate-table-dispatcher-sample"></a>Dispatcher di esempio nella tabella UriTemplate
La classe <xref:System.UriTemplateTable> fornisce una struttura con tabella associativa simile a un dizionario per lavorare con un set di istanze <xref:System.UriTemplate>. In questo esempio viene illustrato un motore di distribuzione di base compilato utilizzando `UriTemplateTable`, uno scenario di utilizzo comune per la classe `UriTemplateTable`.  
  
 In questo esempio vengono illustrati i seguenti concetti principali relativi alla classe `UriTemplateTable`:  
  
-   Associazione di delegati a `UriTemplates` in un `UriTemplateTable`.  
  
-   Utilizzo di <xref:System.UriTemplateTable.MatchSingle%2A> per ottenere il delegato del gestore corretto per un particolare URI.  
  
-   Chiamata al delegato del gestore per elaborare la richiesta.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a>Vedere anche  
 [UriTemplateTable](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
