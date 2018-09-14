---
title: Ritardo durevole in XAMLX
ms.date: 03/30/2017
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
ms.openlocfilehash: 1eef9211c67d190ecb5f329c481fa2e3d1763353
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45594107"
---
# <a name="durable-delay-in-xamlx"></a>Ritardo durevole in XAMLX
In questo esempio viene illustrato come usare un ritardo durevole, ovvero un ritardo che rende persistente il flusso di lavoro in un dispositivo durevole durante il ritardo.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a>Discussione  
 Il flusso di lavoro di esempio contiene due messaggi in un file locale separati da un ritardo. Quando viene attivato il ritardo, il flusso di lavoro viene scaricato e attende 5 secondi nell'archivio di istanze del flusso di lavoro prima di essere ricaricato in memoria.  
  
 Il file con estensione xamlx è un servizio del flusso di lavoro ospitata in Visual Studio. Visual Studio utilizza Cassini che usa un servizio del flusso di lavoro host per ospitare il flusso di lavoro.  
  
 Oltre a ospitare il flusso di lavoro, l'host del servizio flusso di lavoro gestisce le istanze del flusso di lavoro caricandole e scaricandole. Per avviare un'istanza della definizione di Windows Workflow Foundation (WF) (nell'host del servizio del flusso di lavoro), impostare un client che invia un messaggio per il <xref:System.ServiceModel.Activities.Receive> attività nel flusso di lavoro. Questo oggetto <xref:System.ServiceModel.Activities.Receive> dispone della proprietà <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> impostata su `true` in modo che possa creare una nuova istanza del flusso di lavoro dopo aver ricevuto un messaggio.  
  
 Durante l'inizializzazione, viene aggiunto un comportamento di scaricamento di istanze al file di configurazione che specifica all'host del servizio flusso di lavoro il punto in cui scaricare un'istanza nell'archivio di persistenza (database). Per questo esempio, scarica immediatamente l'istanza dopo che il flusso di lavoro diventa inattivo (quando viene attivato il ritardo).  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Passare alla cartella DurableDelayXamlx\CS.  
  
3.  Eseguire Setup.cmd.  
  
4.  Eseguire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] come amministratore.  
  
5.  Aprire il file della soluzione DurableDelayXamlx.sln.  
  
6.  Nelle **Esplora soluzioni**, la soluzione e scegliere **proprietà**.  
  
7.  Selezionare **progetti di avvio multipli** e impostare entrambi i progetti **avviare**.  
  
8.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
9. Per eseguire la soluzione, premere CTRL+F5.  
  
#### <a name="to-uninstall-this-sample"></a>Per disinstallare l'esempio  
  
1.  Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Passare alla cartella DurableDelayXamlx\CS.  
  
3.  Eseguire Cleanup.cmd.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
