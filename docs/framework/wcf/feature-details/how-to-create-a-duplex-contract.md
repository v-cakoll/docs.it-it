---
title: 'Procedura: creare un contratto duplex'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
ms.openlocfilehash: e5b6c7eecce08a23490b6ab1991e4561d9462469
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598983"
---
# <a name="how-to-create-a-duplex-contract"></a><span data-ttu-id="40119-102">Procedura: creare un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="40119-102">How to: Create a Duplex Contract</span></span>
<span data-ttu-id="40119-103">In questo argomento vengono illustrati i passaggi di base per creare metodi che utilizzano un contratto duplex (bidirezionale).</span><span class="sxs-lookup"><span data-stu-id="40119-103">This topic shows the basic steps to create methods that use a duplex (two-way) contract.</span></span> <span data-ttu-id="40119-104">Un contratto duplex consente ai client e ai server di comunicare tra loro in modo indipendente, affinché siano entrambi in grado di effettuare chiamate all'altro.</span><span class="sxs-lookup"><span data-stu-id="40119-104">A duplex contract allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="40119-105">Il contratto duplex è uno dei tre modelli di messaggi disponibili per i servizi Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="40119-105">The duplex contract is one of three message patterns available to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="40119-106">Gli altri due modelli sono il modello unidirezionale e il modello request/reply.</span><span class="sxs-lookup"><span data-stu-id="40119-106">The other two message patterns are one-way and request-reply.</span></span> <span data-ttu-id="40119-107">Un contratto duplex è costituito da due contratti unidirezionali tra il client e il server e non richiede che le chiamate al metodo siano correlate.</span><span class="sxs-lookup"><span data-stu-id="40119-107">A duplex contract consists of two one-way contracts between the client and the server and does not require that the method calls be correlated.</span></span> <span data-ttu-id="40119-108">Utilizzare questo tipo di contratto quando il servizio deve richiedere al client ulteriori informazioni o generare in modo esplicito eventi sul client.</span><span class="sxs-lookup"><span data-stu-id="40119-108">Use this kind of contract when your service must query the client for more information or explicitly raise events on the client.</span></span> <span data-ttu-id="40119-109">Per ulteriori informazioni sulla creazione di un'applicazione client per un contratto duplex, vedere [procedura: accedere ai servizi con un contratto duplex](how-to-access-services-with-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="40119-109">For more information about creating a client application for a duplex contract, see [How to: Access Services with a Duplex Contract](how-to-access-services-with-a-duplex-contract.md).</span></span> <span data-ttu-id="40119-110">Per un esempio funzionante, vedere l'esempio [duplex](../samples/duplex.md) .</span><span class="sxs-lookup"><span data-stu-id="40119-110">For a working sample, see the [Duplex](../samples/duplex.md) sample.</span></span>  
  
### <a name="to-create-a-duplex-contract"></a><span data-ttu-id="40119-111">Per creare un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="40119-111">To create a duplex contract</span></span>  
  
1. <span data-ttu-id="40119-112">Creare l'interfaccia che rappresenta il lato server del contratto duplex.</span><span class="sxs-lookup"><span data-stu-id="40119-112">Create the interface that makes up the server side of the duplex contract.</span></span>  
  
2. <span data-ttu-id="40119-113">Applicare la classe <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="40119-113">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3. <span data-ttu-id="40119-114">Dichiarare le firme del metodo nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="40119-114">Declare the method signatures in the interface.</span></span>  
  
4. <span data-ttu-id="40119-115">Applicare la classe <xref:System.ServiceModel.OperationContractAttribute> a ogni firma del metodo che deve essere parte del contratto pubblico.</span><span class="sxs-lookup"><span data-stu-id="40119-115">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
5. <span data-ttu-id="40119-116">Creare l'interfaccia di callback che definisce il set di operazioni che il servizio può richiamare nel client.</span><span class="sxs-lookup"><span data-stu-id="40119-116">Create the callback interface that defines the set of operations that the service can invoke on the client.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6. <span data-ttu-id="40119-117">Dichiarare le firme del metodo nell'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="40119-117">Declare the method signatures in the callback interface.</span></span>  
  
7. <span data-ttu-id="40119-118">Applicare la classe <xref:System.ServiceModel.OperationContractAttribute> a ogni firma del metodo che deve essere parte del contratto pubblico.</span><span class="sxs-lookup"><span data-stu-id="40119-118">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
8. <span data-ttu-id="40119-119">Collegare le due interfacce in un contratto duplex impostando la proprietà <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> nell'interfaccia primaria sul tipo dell'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="40119-119">Link the two interfaces into a duplex contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> property in the primary interface to the type of the callback interface.</span></span>  
  
### <a name="to-call-methods-on-the-client"></a><span data-ttu-id="40119-120">Per chiamare i metodi nel client.</span><span class="sxs-lookup"><span data-stu-id="40119-120">To call methods on the client</span></span>  
  
1. <span data-ttu-id="40119-121">Nell'implementazione del servizio del contratto primario, dichiarare una variabile per l'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="40119-121">In the service's implementation of the primary contract, declare a variable for the callback interface.</span></span>  
  
2. <span data-ttu-id="40119-122">Impostare la variabile sul riferimento dell'oggetto restituito dal metodo <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> della classe <xref:System.ServiceModel.OperationContext>.</span><span class="sxs-lookup"><span data-stu-id="40119-122">Set the variable to the object reference returned by the <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> method of the <xref:System.ServiceModel.OperationContext> class.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3. <span data-ttu-id="40119-123">Chiamare i metodi definiti dall'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="40119-123">Call the methods defined by the callback interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40119-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="40119-124">Example</span></span>  
 <span data-ttu-id="40119-125">Nell'esempio di codice seguente viene illustrata la comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="40119-125">The following code example demonstrates duplex communication.</span></span> <span data-ttu-id="40119-126">Il contratto del servizio contiene le operazioni del servizio per spostarsi avanti e indietro.</span><span class="sxs-lookup"><span data-stu-id="40119-126">The service’s contract contains service operations for moving forward and backward.</span></span> <span data-ttu-id="40119-127">Il contratto del client contiene un'operazione del servizio per segnalare la sua posizione.</span><span class="sxs-lookup"><span data-stu-id="40119-127">The client’s contract contains a service operation for reporting its position.</span></span>  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
- <span data-ttu-id="40119-128">L'applicazione degli attributi <xref:System.ServiceModel.ServiceContractAttribute> e <xref:System.ServiceModel.OperationContractAttribute> consente di generare automaticamente le definizioni del contratto di servizio nel linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language).</span><span class="sxs-lookup"><span data-stu-id="40119-128">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes allows the automatic generation of service contract definitions in the Web Services Description Language (WSDL).</span></span>  
  
- <span data-ttu-id="40119-129">Utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per recuperare il documento WSDL e (facoltativo) il codice e la configurazione di un client.</span><span class="sxs-lookup"><span data-stu-id="40119-129">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to retrieve the WSDL document and (optional) code and configuration for a client.</span></span>  
  
- <span data-ttu-id="40119-130">Gli endpoint che espongono servizi duplex devono essere protetti.</span><span class="sxs-lookup"><span data-stu-id="40119-130">Endpoints exposing duplex services must be secured.</span></span> <span data-ttu-id="40119-131">Quando un servizio riceve un messaggio duplex, analizza l'elemento ReplyTo contenuto nel messaggio in arrivo per stabilire dove inviare la replica.</span><span class="sxs-lookup"><span data-stu-id="40119-131">When a service receives a duplex message, it looks at the ReplyTo in that incoming message to determine where to send the reply.</span></span> <span data-ttu-id="40119-132">Se il canale non è protetto, un client non attendibile potrebbe inviare un messaggio dannoso con un elemento ReplyTo del computer di destinazione, il che comporta un Denial of Service (DoS) del computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="40119-132">If the channel is not secured, then an untrusted client could send a malicious message with a target machine's ReplyTo, leading to a denial of service of the target machine.</span></span> <span data-ttu-id="40119-133">Con i messaggi request/reply normali, questo non è un problema, perché ReplyTo viene ignorato e la risposta viene inviata sul canale sul quale è arrivato il messaggio originale.</span><span class="sxs-lookup"><span data-stu-id="40119-133">With regular request-reply messages, this is not an issue, because the ReplyTo is ignored and the response is sent on the channel the original message came in on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40119-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40119-134">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="40119-135">Procedura: accedere ai servizi con un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="40119-135">How to: Access Services with a Duplex Contract</span></span>](how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="40119-136">Duplex</span><span class="sxs-lookup"><span data-stu-id="40119-136">Duplex</span></span>](../samples/duplex.md)
- [<span data-ttu-id="40119-137">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="40119-137">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)
- [<span data-ttu-id="40119-138">Procedura: Definire un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="40119-138">How to: Define a Service Contract</span></span>](../how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="40119-139">Sessione</span><span class="sxs-lookup"><span data-stu-id="40119-139">Session</span></span>](../samples/session.md)
