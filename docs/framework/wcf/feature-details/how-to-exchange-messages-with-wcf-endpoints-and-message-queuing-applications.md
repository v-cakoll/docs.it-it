---
title: 'Procedura: scambiare messaggi con endpoint WCF e con applicazioni del sistema di accodamento dei messaggi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 0775de90903aed27a8d0006614a4b6f2d857eee3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597098"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a>Procedura: scambiare messaggi con endpoint WCF e con applicazioni del sistema di accodamento dei messaggi
È possibile integrare le applicazioni di Accodamento messaggi (MSMQ) esistenti con le applicazioni Windows Communication Foundation (WCF) utilizzando l'associazione di integrazione MSMQ per convertire i messaggi MSMQ da e verso messaggi WCF. In questo modo è possibile chiamare le applicazioni Receiver MSMQ dai client WCF e chiamare i servizi WCF dalle applicazioni mittente MSMQ.  
  
 In questa sezione viene illustrato come utilizzare per la <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> comunicazione in coda tra (1) un client WCF e un servizio dell'applicazione MSMQ scritto utilizzando System. Messaging e (2) un client dell'applicazione MSMQ e un servizio WCF.  
  
 Per un esempio completo in cui viene illustrato come chiamare un'applicazione Receiver MSMQ da un client WCF, vedere l'esempio [Windows Communication Foundation a Accodamento messaggi](../samples/wcf-to-message-queuing.md) .  
  
 Per un esempio completo in cui viene illustrato come chiamare un servizio WCF da un client MSMQ, vedere l'esempio [di Accodamento messaggi a Windows Communication Foundation](../samples/message-queuing-to-wcf.md) .  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>Per creare un servizio WCF che riceve messaggi da un client MSMQ  
  
1. Definire un'interfaccia che definisce il contratto di servizio per il servizio WCF che riceve i messaggi in coda da un'applicazione mittente MSMQ, come illustrato nel codice di esempio seguente.  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2. Implementare l'interfaccia e applicare l'attributo <xref:System.ServiceModel.ServiceBehaviorAttribute> alla classe, come mostrato nell'esempio di codice seguente.  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3. Creare un file di configurazione che specifica l'associazione <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.  

4. Creare un'istanza di un oggetto <xref:System.ServiceModel.ServiceHost> che utilizza l'associazione configurata.  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>Per creare un client WCF che invia messaggi a un'applicazione MSMQ ricevente  
  
1. Definire un'interfaccia che definisce il contratto di servizio per il client WCF che invia messaggi in coda al ricevitore MSMQ, come illustrato nel codice di esempio seguente.  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2. Definire una classe client utilizzata dal client WCF per chiamare il ricevitore MSMQ.  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3. Creare una configurazione che specifichi l'utilizzo dell'associazione MsmqIntegrationBinding.  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4. Creare un'istanza della classe client e chiamare il metodo definito dal servizio che riceve i messaggi.  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica delle code](queues-overview.md)
- [Procedura: scambiare messaggi in coda con endpoint WCF](how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [Da Windows Communication Foundation a Accodamento messaggi](../samples/wcf-to-message-queuing.md)
- [Installazione accodamento messaggi (MSMQ)](../samples/installing-message-queuing-msmq.md)
- [Accodamento messaggi in Windows Communication Foundation](../samples/message-queuing-to-wcf.md)
- [Sicurezza dei messaggi nell'accodamento messaggi](../samples/message-security-over-message-queuing.md)
