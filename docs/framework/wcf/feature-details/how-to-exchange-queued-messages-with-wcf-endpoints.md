---
title: 'Procedura: Lo scambio di messaggi in coda con endpoint WCF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
ms.openlocfilehash: 9ee071eb88be504f7fde29b61d3a39327f0b467f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693438"
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a>Procedura: Lo scambio di messaggi in coda con endpoint WCF
Le code garantiscono che la messaggistica affidabile può verificarsi tra un client e un servizio Windows Communication Foundation (WCF), anche se il servizio non è disponibile al momento della comunicazione. Le procedure seguenti illustrano come assicurare una comunicazione durevole tra un client e un servizio utilizzando lo standard di associazione in coda quando si implementa il servizio WCF.  
  
 In questa sezione illustra come usare <xref:System.ServiceModel.NetMsmqBinding> per la comunicazione in coda tra un client WCF e un servizio WCF.  
  
### <a name="to-use-queuing-in-a-wcf-service"></a>Per utilizzare l'accodamento in un servizio WCF  
  
1.  Definire un contratto di servizio utilizzando un'interfaccia contrassegnata con <xref:System.ServiceModel.ServiceContractAttribute>. Contrassegnare con <xref:System.ServiceModel.OperationContractAttribute> le operazioni che nell'interfaccia fanno parte del contratto di servizio e specificare che sono unidirezionali dal momento che non viene restituita alcuna risposta al metodo. Nel codice seguente sono contenuti un esempio di contratto di servizio semplice e la relativa definizione di operazione.  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  Quando il contratto di servizio passa tipi definiti dall'utente, è necessario definire contratti dati per tali tipi. Nel codice seguente vengono illustrati due contratti dati, `PurchaseOrder` e `PurchaseOrderLineItem`. Questi due tipi definiscono i dati inviati al servizio. Si noti che le classi che definiscono questo contratto dati definiscono anche un certo numero di metodi. Questi non vengono considerati parte del contratto dati. Solo i membri che sono dichiarati con l'attributo `DataMember` fanno parte del contratto dati.  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  Implementare i metodi del contratto di servizio definiti nell'interfaccia in una classe.  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     Si noti <xref:System.ServiceModel.OperationBehaviorAttribute> sul metodo `SubmitPurchaseOrder`. In tal modo viene specificato che questa operazione deve essere chiamata all'interno di una transazione e che la transazione viene completata automaticamente quando il metodo è stato completato.  
  
4.  Creare una coda transazionale utilizzando lo spazio dei nomi <xref:System.Messaging>. È possibile scegliere di creare la coda mediante la console MMC (Microsoft Management Console) MSMQ. In tal caso, avere cura di creare una coda transazionale.  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  Definire un oggetto <xref:System.ServiceModel.Description.ServiceEndpoint> nella configurazione che specifichi l'indirizzo del servizio e utilizzi l'associazione <xref:System.ServiceModel.NetMsmqBinding> standard. Per altre informazioni sull'uso di configurazione WCF, vedere [configurazione di applicazioni di Windows Communication Foundation](https://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).  
  
  
  
6.  Creare un host per il servizio `OrderProcessing` utilizzando l'elemento <xref:System.ServiceModel.ServiceHost> che legge i messaggi dalla coda e li elabora. Aprire l'host del servizio per rendere disponibile il servizio. Visualizzare un messaggio che indichi all'utente di premere un tasto qualsiasi per terminare il servizio. Chiamare `ReadLine` per attendere che il tasto venga premuto, quindi chiudere il servizio.  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a>Per creare un client per il servizio in coda  
  
1.  Nell'esempio seguente viene illustrato come eseguire l'applicazione host e utilizzare lo strumento Svcutil.exe per creare il client WCF.  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  Definire un <xref:System.ServiceModel.Description.ServiceEndpoint> nella configurazione che specifichi l'indirizzo e utilizzi l'associazione <xref:System.ServiceModel.NetMsmqBinding> standard, come illustrato nell'esempio seguente.  
  
  
  
3.  Creare un ambito di transazione da scrivere nella coda transazionale, chiamata di `SubmitPurchaseOrder` operazione e chiudere il client WCF, come illustrato nell'esempio seguente.  
  
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
- [Associazioni MSMQ transazionali](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)
- [Accodamento in WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
- [Procedura: Scambiare messaggi con endpoint WCF e le applicazioni di Accodamento messaggi](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [Da Windows Communication Foundation a Accodamento messaggi](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)
- [Installazione accodamento messaggi (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)
- [Esempi di associazione di integrazione dell'accodamento dei messaggi](https://msdn.microsoft.com/library/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)
- [Accodamento messaggi in Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)
- [Sicurezza dei messaggi nell'accodamento messaggi](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
