---
title: 'Procedura: scambiare messaggi in coda con endpoint WCF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
ms.openlocfilehash: 7da7ba1b680bae2b29eeff8fe669e097ea8eda32
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595375"
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a>Procedura: scambiare messaggi in coda con endpoint WCF
Le code assicurano che la messaggistica affidabile possa essere eseguita tra un client e un servizio Windows Communication Foundation (WCF), anche se il servizio non è disponibile al momento della comunicazione. Nelle procedure riportate di seguito viene illustrato come garantire la comunicazione durevole tra un client e un servizio utilizzando l'associazione in coda standard durante l'implementazione del servizio WCF.  
  
 In questa sezione viene illustrato come utilizzare <xref:System.ServiceModel.NetMsmqBinding> per la comunicazione in coda tra un client WCF e un servizio WCF.  
  
### <a name="to-use-queuing-in-a-wcf-service"></a>Per utilizzare l'accodamento in un servizio WCF  
  
1. Definire un contratto di servizio utilizzando un'interfaccia contrassegnata con <xref:System.ServiceModel.ServiceContractAttribute>. Contrassegnare con <xref:System.ServiceModel.OperationContractAttribute> le operazioni che nell'interfaccia fanno parte del contratto di servizio e specificare che sono unidirezionali dal momento che non viene restituita alcuna risposta al metodo. Nel codice seguente sono contenuti un esempio di contratto di servizio semplice e la relativa definizione di operazione.  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2. Quando il contratto di servizio passa tipi definiti dall'utente, è necessario definire contratti dati per tali tipi. Nel codice seguente vengono illustrati due contratti dati, `PurchaseOrder` e `PurchaseOrderLineItem`. Questi due tipi definiscono i dati inviati al servizio. Si noti che le classi che definiscono questo contratto dati definiscono anche un certo numero di metodi. Questi non vengono considerati parte del contratto dati. Solo i membri che sono dichiarati con l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> fanno parte del contratto dati.  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3. Implementare i metodi del contratto di servizio definiti nell'interfaccia in una classe.  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     Si noti <xref:System.ServiceModel.OperationBehaviorAttribute> sul metodo `SubmitPurchaseOrder`. In tal modo viene specificato che questa operazione deve essere chiamata all'interno di una transazione e che la transazione viene completata automaticamente quando il metodo è stato completato.  
  
4. Creare una coda transazionale utilizzando lo spazio dei nomi <xref:System.Messaging>. È possibile scegliere di creare la coda mediante la console MMC (Microsoft Management Console) MSMQ. In tal caso, avere cura di creare una coda transazionale.  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5. Definire un oggetto <xref:System.ServiceModel.Description.ServiceEndpoint> nella configurazione che specifichi l'indirizzo del servizio e utilizzi l'associazione <xref:System.ServiceModel.NetMsmqBinding> standard. Per ulteriori informazioni sull'utilizzo della configurazione WCF, vedere [configurazione dei servizi WCF](../configuring-services.md).  

6. Creare un host per il servizio `OrderProcessing` utilizzando l'elemento <xref:System.ServiceModel.ServiceHost> che legge i messaggi dalla coda e li elabora. Aprire l'host del servizio per rendere disponibile il servizio. Visualizzare un messaggio che indichi all'utente di premere un tasto qualsiasi per terminare il servizio. Chiamare `ReadLine` per attendere che il tasto venga premuto, quindi chiudere il servizio.  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a>Per creare un client per il servizio in coda  
  
1. Nell'esempio seguente viene illustrato come eseguire l'applicazione host e utilizzare lo strumento Svcutil. exe per creare il client WCF.  
  
    ```console
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2. Definire un <xref:System.ServiceModel.Description.ServiceEndpoint> nella configurazione che specifichi l'indirizzo e utilizzi l'associazione <xref:System.ServiceModel.NetMsmqBinding> standard, come illustrato nell'esempio seguente.  

3. Creare un ambito di transazione per scrivere nella coda transazionale, chiamare l' `SubmitPurchaseOrder` operazione e chiudere il client WCF, come illustrato nell'esempio seguente.  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti vengono illustrati il codice di servizio, l'applicazione host, il file App.config e il codice client inclusi per questo esempio.  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  

 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.NetMsmqBinding>
- [Associazioni MSMQ transazionali](../samples/transacted-msmq-binding.md)
- [Accodamento in WCF](queuing-in-wcf.md)
- [Procedura: scambiare messaggi con endpoint WCF e con applicazioni del sistema di accodamento dei messaggi](how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [Da Windows Communication Foundation a Accodamento messaggi](../samples/wcf-to-message-queuing.md)
- [Installazione accodamento messaggi (MSMQ)](../samples/installing-message-queuing-msmq.md)
- [Accodamento messaggi in Windows Communication Foundation](../samples/message-queuing-to-wcf.md)
- [Sicurezza dei messaggi nell'accodamento messaggi](../samples/message-security-over-message-queuing.md)
