---
title: Calcolatrice correlata
ms.date: 03/30/2017
ms.assetid: c365166e-6552-49a4-bf17-9f4e597d4d41
ms.openlocfilehash: 77e13b3ca913d2432cfe5d4a95e83764effbb109
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514141"
---
# <a name="correlated-calculator"></a>Calcolatrice correlata
In questo esempio viene illustrato come usare le attività di messaggistica (<xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply>) nella finestra di progettazione con correlazione basata sul contenuto in base a un parametro nel messaggio. In questo scenario, le operazioni della calcolatrice sono in una serie di istruzioni parallele. Sia un'istanza sia una correlazione (basate su `CalculatorId`) vengono create quando viene inviato il primo messaggio al flusso di lavoro mentre i messaggi successivi con lo stesso `CalculatorId` vengono inviati a tale istanza fino a quando non viene chiamata l'operazione di reimpostazione. Il client viene implementato come applicazione WPF che usa un proxy client basato su codice per comunicare con il servizio.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Avviare [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] nelle autorizzazioni elevate e aprire il file della soluzione For.sln.  
  
    1.  Passare alla cartella che contiene [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    2.  Fare doppio clic su Devenv.exe e selezionare **Esegui come amministratore**.  
  
2.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione CorrelatedCalculator.sln.  
  
3.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
4.  Per eseguire il progetto servizio, premere CTRL+F5.  
  
5.  Una volta che servizio è pronto e in attesa dei messaggi, in Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto Client ed eseguirlo.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\CorellatedCalculator`