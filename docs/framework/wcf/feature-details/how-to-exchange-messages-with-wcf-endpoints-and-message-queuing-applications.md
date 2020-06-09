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
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a><span data-ttu-id="69f18-102">Procedura: scambiare messaggi con endpoint WCF e con applicazioni del sistema di accodamento dei messaggi</span><span class="sxs-lookup"><span data-stu-id="69f18-102">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>
<span data-ttu-id="69f18-103">È possibile integrare le applicazioni di Accodamento messaggi (MSMQ) esistenti con le applicazioni Windows Communication Foundation (WCF) utilizzando l'associazione di integrazione MSMQ per convertire i messaggi MSMQ da e verso messaggi WCF.</span><span class="sxs-lookup"><span data-stu-id="69f18-103">You can integrate existing Message Queuing (MSMQ) applications with Windows Communication Foundation (WCF) applications by using the MSMQ integration binding to convert MSMQ messages to and from WCF messages.</span></span> <span data-ttu-id="69f18-104">In questo modo è possibile chiamare le applicazioni Receiver MSMQ dai client WCF e chiamare i servizi WCF dalle applicazioni mittente MSMQ.</span><span class="sxs-lookup"><span data-stu-id="69f18-104">This allows you to call into MSMQ receiver applications from WCF clients as well as call into WCF services from MSMQ sender applications.</span></span>  
  
 <span data-ttu-id="69f18-105">In questa sezione viene illustrato come utilizzare per la <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> comunicazione in coda tra (1) un client WCF e un servizio dell'applicazione MSMQ scritto utilizzando System. Messaging e (2) un client dell'applicazione MSMQ e un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="69f18-105">In this section, we explain how to use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> for queued communication between (1) a WCF client and an MSMQ application service written using System.Messaging and (2) an MSMQ application client and a WCF service.</span></span>  
  
 <span data-ttu-id="69f18-106">Per un esempio completo in cui viene illustrato come chiamare un'applicazione Receiver MSMQ da un client WCF, vedere l'esempio [Windows Communication Foundation a Accodamento messaggi](../samples/wcf-to-message-queuing.md) .</span><span class="sxs-lookup"><span data-stu-id="69f18-106">For a complete sample that demonstrates how to call a MSMQ receiver application from a WCF client, see the [Windows Communication Foundation to Message Queuing](../samples/wcf-to-message-queuing.md) sample.</span></span>  
  
 <span data-ttu-id="69f18-107">Per un esempio completo in cui viene illustrato come chiamare un servizio WCF da un client MSMQ, vedere l'esempio [di Accodamento messaggi a Windows Communication Foundation](../samples/message-queuing-to-wcf.md) .</span><span class="sxs-lookup"><span data-stu-id="69f18-107">For a complete sample that demonstrates how to call a WCF service from a MSMQ client, see the [Message Queuing to Windows Communication Foundation](../samples/message-queuing-to-wcf.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a><span data-ttu-id="69f18-108">Per creare un servizio WCF che riceve messaggi da un client MSMQ</span><span class="sxs-lookup"><span data-stu-id="69f18-108">To create a WCF service that receives messages from a MSMQ client</span></span>  
  
1. <span data-ttu-id="69f18-109">Definire un'interfaccia che definisce il contratto di servizio per il servizio WCF che riceve i messaggi in coda da un'applicazione mittente MSMQ, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="69f18-109">Define an interface that defines the service contract for the WCF service that receives queued messages from a MSMQ sender application, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2. <span data-ttu-id="69f18-110">Implementare l'interfaccia e applicare l'attributo <xref:System.ServiceModel.ServiceBehaviorAttribute> alla classe, come mostrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="69f18-110">Implement the interface and apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the class, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3. <span data-ttu-id="69f18-111">Creare un file di configurazione che specifica l'associazione <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span><span class="sxs-lookup"><span data-stu-id="69f18-111">Create a configuration file that specifies the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span>  

4. <span data-ttu-id="69f18-112">Creare un'istanza di un oggetto <xref:System.ServiceModel.ServiceHost> che utilizza l'associazione configurata.</span><span class="sxs-lookup"><span data-stu-id="69f18-112">Instantiate a <xref:System.ServiceModel.ServiceHost> object that uses the configured binding.</span></span>  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a><span data-ttu-id="69f18-113">Per creare un client WCF che invia messaggi a un'applicazione MSMQ ricevente</span><span class="sxs-lookup"><span data-stu-id="69f18-113">To create a WCF client that sends messages to a MSMQ receiver application</span></span>  
  
1. <span data-ttu-id="69f18-114">Definire un'interfaccia che definisce il contratto di servizio per il client WCF che invia messaggi in coda al ricevitore MSMQ, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="69f18-114">Define an interface that defines the service contract for the WCF client that sends queued messages to the MSMQ receiver, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2. <span data-ttu-id="69f18-115">Definire una classe client utilizzata dal client WCF per chiamare il ricevitore MSMQ.</span><span class="sxs-lookup"><span data-stu-id="69f18-115">Define a client class that the WCF client uses to call the MSMQ receiver.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3. <span data-ttu-id="69f18-116">Creare una configurazione che specifichi l'utilizzo dell'associazione MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="69f18-116">Create a configuration that specifies use of the MsmqIntegrationBinding binding.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4. <span data-ttu-id="69f18-117">Creare un'istanza della classe client e chiamare il metodo definito dal servizio che riceve i messaggi.</span><span class="sxs-lookup"><span data-stu-id="69f18-117">Create an instance of the client class and call the method defined by the message receiving service.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="69f18-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69f18-118">See also</span></span>

- [<span data-ttu-id="69f18-119">Panoramica delle code</span><span class="sxs-lookup"><span data-stu-id="69f18-119">Queues Overview</span></span>](queues-overview.md)
- [<span data-ttu-id="69f18-120">Procedura: scambiare messaggi in coda con endpoint WCF</span><span class="sxs-lookup"><span data-stu-id="69f18-120">How to: Exchange Queued Messages with WCF Endpoints</span></span>](how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [<span data-ttu-id="69f18-121">Da Windows Communication Foundation a Accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="69f18-121">Windows Communication Foundation to Message Queuing</span></span>](../samples/wcf-to-message-queuing.md)
- [<span data-ttu-id="69f18-122">Installazione accodamento messaggi (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="69f18-122">Installing Message Queuing (MSMQ)</span></span>](../samples/installing-message-queuing-msmq.md)
- [<span data-ttu-id="69f18-123">Accodamento messaggi in Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="69f18-123">Message Queuing to Windows Communication Foundation</span></span>](../samples/message-queuing-to-wcf.md)
- [<span data-ttu-id="69f18-124">Sicurezza dei messaggi nell'accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="69f18-124">Message Security over Message Queuing</span></span>](../samples/message-security-over-message-queuing.md)
