---
title: Dispatcher di esempio nella tabella UriTemplate
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: 4a4f725e88e014da241e1042c27bfee270e13268
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44337408"
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
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a>Vedere anche  
 [UriTemplateTable](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
