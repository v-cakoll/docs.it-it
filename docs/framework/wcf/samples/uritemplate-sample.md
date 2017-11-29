---
title: Esempio di UriTemplate
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 729a48fe0ea34bf1630824d941341fff82ade1ef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="uritemplate-sample"></a>Esempio di UriTemplate
La classe <xref:System.UriTemplate> fornisce metodi per l'utilizzo di set di URI che condividono una struttura comune. In questo esempio vengono illustrati i seguenti concetti principali relativi a `UriTemplate`:  
  
-   Sintassi per la creazione di modelli.  
  
-   Creazione di istanze degli URI da un `UriTemplate` utilizzando <xref:System.UriTemplate.BindByName%2A> e <xref:System.UriTemplate.BindByPosition%2A>.  
  
-   <xref:System.UriTemplateTable.Match%2A>, che corrisponde all'operazione inversa di `BindByName` e `BindByPosition`.  
  
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
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a>Vedere anche  
 [Tabella UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [Dispatcher della tabella UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
