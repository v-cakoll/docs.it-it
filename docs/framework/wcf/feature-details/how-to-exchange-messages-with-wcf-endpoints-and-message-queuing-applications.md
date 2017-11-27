---
title: 'Procedura: scambiare messaggi con endpoint WCF e con applicazioni del sistema di accodamento dei messaggi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d09b8e662b2876fa5d5c5246ea7e7a4998cde9ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a><span data-ttu-id="120dc-102">Procedura: scambiare messaggi con endpoint WCF e con applicazioni del sistema di accodamento dei messaggi</span><span class="sxs-lookup"><span data-stu-id="120dc-102">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>
<span data-ttu-id="120dc-103">Per integrare le applicazioni esistenti del sistema di accodamento dei messaggi (MSMQ) con le applicazioni di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è possibile utilizzare l'associazione di integrazione con MSMQ per convertire i messaggi MSMQ in messaggi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e viceversa.</span><span class="sxs-lookup"><span data-stu-id="120dc-103">You can integrate existing Message Queuing (MSMQ) applications with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] applications by using the MSMQ integration binding to convert MSMQ messages to and from [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] messages.</span></span> <span data-ttu-id="120dc-104">Ciò consente di chiamare applicazioni MSMQ riceventi tramite un client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nonché chiamare servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tramite applicazioni MSMQ mittenti.</span><span class="sxs-lookup"><span data-stu-id="120dc-104">This allows you to call into MSMQ receiver applications from [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients as well as call into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services from MSMQ sender applications.</span></span>  
  
 <span data-ttu-id="120dc-105">Contenuto della sezione viene descritto come utilizzare l'associazione <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> per la comunicazione in coda tra (1) un client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e un'applicazione MSMQ server scritta utilizzando System.Messaging e (2) un'applicazione MSMQ client e un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="120dc-105">In this section, we explain how to use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> for queued communication between (1) a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and an MSMQ application service written using System.Messaging and (2) an MSMQ application client and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="120dc-106">Per un esempio completo che illustra come chiamare un'applicazione MSMQ ricevente da un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, vedere il [Windows Communication Foundation a Accodamento messaggi](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="120dc-106">For a complete sample that demonstrates how to call a MSMQ receiver application from a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, see the [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) sample.</span></span>  
  
 <span data-ttu-id="120dc-107">Per un esempio completo che illustra come chiamare un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] del servizio da un client MSMQ, vedere il [Accodamento messaggi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="120dc-107">For a complete sample that demonstrates how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service from a MSMQ client, see the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a><span data-ttu-id="120dc-108">Per creare un servizio WCF che riceve messaggi da un client MSMQ</span><span class="sxs-lookup"><span data-stu-id="120dc-108">To create a WCF service that receives messages from a MSMQ client</span></span>  
  
1.  <span data-ttu-id="120dc-109">Creare un'interfaccia che definisca il contratto del servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che riceve messaggi in coda da un'applicazione MSMQ mittente, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="120dc-109">Define an interface that defines the service contract for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that receives queued messages from a MSMQ sender application, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  <span data-ttu-id="120dc-110">Implementare l'interfaccia e applicare l'attributo <xref:System.ServiceModel.ServiceBehaviorAttribute> alla classe, come mostrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="120dc-110">Implement the interface and apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the class, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  <span data-ttu-id="120dc-111">Creare un file di configurazione che specifica l'associazione <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span><span class="sxs-lookup"><span data-stu-id="120dc-111">Create a configuration file that specifies the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span>  
  
  
  
4.  <span data-ttu-id="120dc-112">Creare un'istanza di un oggetto <xref:System.ServiceModel.ServiceHost> che utilizza l'associazione configurata.</span><span class="sxs-lookup"><span data-stu-id="120dc-112">Instantiate a <xref:System.ServiceModel.ServiceHost> object that uses the configured binding.</span></span>  
  
  
  
### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a><span data-ttu-id="120dc-113">Per creare un client WCF che invia messaggi a un'applicazione MSMQ ricevente</span><span class="sxs-lookup"><span data-stu-id="120dc-113">To create a WCF client that sends messages to a MSMQ receiver application</span></span>  
  
1.  <span data-ttu-id="120dc-114">Creare un'interfaccia che definisca il contratto di servizio del client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che invii messaggi in coda a un'applicazione MSMQ ricevente, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="120dc-114">Define an interface that defines the service contract for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that sends queued messages to the MSMQ receiver, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  <span data-ttu-id="120dc-115">Definire una classe client che verrà utilizzata dal client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per chiamare l'applicazione MSMQ ricevente.</span><span class="sxs-lookup"><span data-stu-id="120dc-115">Define a client class that the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client uses to call the MSMQ receiver.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  <span data-ttu-id="120dc-116">Creare una configurazione che specifichi l'utilizzo dell'associazione MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="120dc-116">Create a configuration that specifies use of the MsmqIntegrationBinding binding.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  <span data-ttu-id="120dc-117">Creare un'istanza della classe client e chiamare il metodo definito dal servizio che riceve i messaggi.</span><span class="sxs-lookup"><span data-stu-id="120dc-117">Create an instance of the client class and call the method defined by the message receiving service.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="120dc-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="120dc-118">See Also</span></span>  
 [<span data-ttu-id="120dc-119">Panoramica delle code</span><span class="sxs-lookup"><span data-stu-id="120dc-119">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [<span data-ttu-id="120dc-120">Procedura: scambiare messaggi con endpoint WCF in coda</span><span class="sxs-lookup"><span data-stu-id="120dc-120">How to: Exchange Queued Messages with WCF Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [<span data-ttu-id="120dc-121">Windows Communication Foundation a Accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="120dc-121">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="120dc-122">Installazione di Accodamento messaggi (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="120dc-122">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="120dc-123">Accodamento messaggi di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="120dc-123">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="120dc-124">Sicurezza del messaggio su Accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="120dc-124">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
