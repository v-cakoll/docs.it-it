---
title: Correlazione basata sul contenuto
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8638b5d6-1d59-456d-8acd-179a5b39b260
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5971636df3393adda96dff779c1533969f67bf57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="content-based-correlation"></a>Correlazione basata sul contenuto
In questo esempio viene illustrato come è possibile usare le attività di messaggistica (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>e <xref:System.ServiceModel.Activities.ReceiveReply>) con una e con più correlazioni basate sul contenuto. In questo scenario una correlazione viene prima inizializzata in base a un ID dell'ordine di acquisto, quindi in un secondo momento viene creata l'altra correlazione in base all'ID cliente. Illustra come un'attività <xref:System.ServiceModel.Activities.Receive> possa seguire una correlazione esistente e inizializzarne una nuova in base allo stesso messaggio in arrivo.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Attività di messaggistica e correlazione basata sul contenuto  
  
## <a name="discussion"></a>Discussione  
 In questo esempio viene illustrato come usare più correlazioni basate sul contenuto.  In questo scenario una correlazione viene prima inizializzata in base a un ID dell'ordine di acquisto, quindi in un secondo momento viene creata l'altra correlazione in base all'ID cliente.  Le correlazioni vengono sovrapposte usando un'attività <xref:System.ServiceModel.Activities.Receive> che segue una correlazione esistente (PurchaseOrderId) e inizializza una nuova correlazione (CustomerID) in base allo stesso messaggio in arrivo.  Per eseguire questa operazione, nell'attività <xref:System.ServiceModel.Activities.Receive> vengono usate le proprietà <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> e <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>.  
  
## <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con autorizzazioni elevate facendo clic con il [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e selezionando **Esegui come amministratore**.  
  
2.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione CascadingCorrelation.sln.  
  
3.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
4.  Per eseguire il server, premere F5.  
  
5.  Una volta che servizio è pronto e in attesa dei messaggi, in Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto Client ed eseguirlo.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ContentBasedCorrelation`