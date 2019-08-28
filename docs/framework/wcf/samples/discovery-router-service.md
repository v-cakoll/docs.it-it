---
title: Servizio router di individuazione
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: 9434c26fb12b73ea4f1c185658b03cb95a3a2310
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70039823"
---
# <a name="discovery-router-service"></a>Servizio router di individuazione
In questo esempio viene descritto come inoltrare messaggi di individuazione a un altro endpoint.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Routing di individuazione  
  
## <a name="discussion"></a>Discussione  
 Il routing di individuazione è utile in uno scenario nel quale un client effettua la ricerca di un servizio utilizzando un proxy e il proxy non riconosce tale servizio, ma riconosce un altro proxy. Questo proxy può inoltrare il pacchetto di individuazione dal client al secondo proxy. Il secondo proxy può ricercare il servizio e restituire le risposte al client originale.  
  
 In questo esempio, un client invia un messaggio a un componente del routing di individuazione. Il messaggio viene inviato a un endpoint specifico nel router di individuazione. Il router inoltra quindi il messaggio a un endpoint multicast UDP. Il messaggio del probe raggiunge l'endpoint multicast e un servizio in ascolto su un indirizzo multicast UDP risponde al router di individuazione. Il router di individuazione raccoglie le risposte e le restituisce al client.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Compilare l'esempio.  
  
2. Eseguire il file eseguibile DiscoveryRouter.  
  
3. Eseguire il servizio eseguibile dalla directory di compilazione.  
  
4. Eseguire il file eseguibile del client. Il client individua il servizio.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
