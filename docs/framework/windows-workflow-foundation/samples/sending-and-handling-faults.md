---
title: Invio e gestione di errori
ms.date: 03/30/2017
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
ms.openlocfilehash: 6796b4daccd88adc3bd006f454ce96ca155fbcb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516126"
---
# <a name="sending-and-handling-faults"></a>Invio e gestione di errori
In questo esempio viene illustrato come usare le attività di messaggistica <xref:System.ServiceModel.Activities.SendReply> e <xref:System.ServiceModel.Activities.ReceiveReply> per inviare e ricevere errori previsti e imprevisti. In questo scenario, la prima richiesta del client comporta un errore previsto incluso nella raccolta <xref:System.ServiceModel.Activities.Send.KnownTypes%2A>. Le successive richieste del client comportano la ricezione di errori imprevisti, prima del completamento della richiesta finale.  
  
## <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con autorizzazioni elevate facendo clic con il [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e selezionando **Esegui come amministratore**.  
  
2.  Aprire il file della soluzione Faults.sln.  
  
3.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
4.  Eseguire il progetto del servizio.  
  
    1.  In **Esplora**, fare doppio clic su di `FaultService` del progetto e selezionare **imposta come progetto di avvio**.  
  
    2.  Premere CTRL+F5.  
  
5.  Aprire un'altra copia del [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con autorizzazioni elevate facendo clic con il [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e selezionando **Esegui come amministratore**.  
  
6.  Aprire il file della soluzione Faults.sln.  
  
7.  Eseguire il progetto del client.  
  
    1.  In **Esplora**, fare doppio clic su di `FaultClient` del progetto e selezionare **imposta come progetto di avvio**.  
  
    2.  Premere CTRL+F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`