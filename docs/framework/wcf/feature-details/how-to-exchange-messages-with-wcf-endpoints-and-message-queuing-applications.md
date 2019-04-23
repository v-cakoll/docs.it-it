---
title: 'Procedura: Scambiare messaggi con endpoint WCF e con applicazioni di accodamento dei messaggi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 7463f9cfc37c2bf4f271f6e59896a7d77f3f65cd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59310304"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a>Procedura: Scambiare messaggi con endpoint WCF e con applicazioni di accodamento dei messaggi
È possibile integrare le applicazioni di Accodamento messaggi (MSMQ) esistenti con le applicazioni di Windows Communication Foundation (WCF) utilizzando l'associazione di integrazione MSMQ per convertire i messaggi MSMQ in e da messaggi WCF. In questo modo è possibile chiamare applicazioni MSMQ riceventi dai client WCF, nonché chiamare servizi WCF da applicazioni MSMQ mittenti.  
  
 In questa sezione viene illustrato come usare <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> per la comunicazione in coda tra (1) un client WCF e il servizio di un'applicazione MSMQ scritta utilizzando System. Messaging e (2) un'applicazione MSMQ client e un servizio WCF.  
  
 Per un esempio completo che illustra come chiamare un'applicazione MSMQ ricevente da un client WCF, vedere la [Windows Communication Foundation a Accodamento messaggi](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) esempio.  
  
 Per un esempio completo che illustra come chiamare un servizio WCF da un client MSMQ, vedere la [Accodamento messaggi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) esempio.  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>Per creare un servizio WCF che riceve messaggi da un client MSMQ  
  
1. Definire un'interfaccia che definisce il contratto di servizio per il servizio WCF che riceve i messaggi in coda da un'applicazione MSMQ mittente, come illustrato nell'esempio di codice seguente.  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2. Implementare l'interfaccia e applicare l'attributo <xref:System.ServiceModel.ServiceBehaviorAttribute> alla classe, come mostrato nell'esempio di codice seguente.  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3. Creare un file di configurazione che specifica l'associazione <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.  

4. Creare un'istanza di un oggetto <xref:System.ServiceModel.ServiceHost> che utilizza l'associazione configurata.  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>Per creare un client WCF che invia messaggi a un'applicazione MSMQ ricevente  
  
1. Definire un'interfaccia che definisce il contratto di servizio per il client WCF che inviati in coda i messaggi per l'applicazione MSMQ ricevente, come illustrato nell'esempio di codice seguente.  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2. Definire una classe client che usa il client WCF per chiamare l'applicazione MSMQ ricevente.  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3. Creare una configurazione che specifichi l'utilizzo dell'associazione MsmqIntegrationBinding.  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4. Creare un'istanza della classe client e chiamare il metodo definito dal servizio che riceve i messaggi.  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica delle code](../../../../docs/framework/wcf/feature-details/queues-overview.md)
- [Procedura: Lo scambio di messaggi in coda con endpoint WCF](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [Da Windows Communication Foundation a Accodamento messaggi](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)
- [Installazione accodamento messaggi (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)
- [Accodamento messaggi in Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)
- [Sicurezza dei messaggi nell'accodamento messaggi](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
