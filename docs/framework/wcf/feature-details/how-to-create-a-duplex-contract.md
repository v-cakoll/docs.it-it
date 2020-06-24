---
title: 'Procedura: creare un contratto duplex'
description: Informazioni su come creare un contratto duplex, che consente a client e server WCF di comunicare tra loro in modo indipendente. In entrambi i casi è possibile avviare chiamate all'altra.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
ms.openlocfilehash: 9320e5b36b8faba3602fbe1df1b95c05dcc7fa7e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247091"
---
# <a name="how-to-create-a-duplex-contract"></a><span data-ttu-id="b25fe-104">Procedura: creare un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="b25fe-104">How to: Create a Duplex Contract</span></span>
<span data-ttu-id="b25fe-105">In questo argomento vengono illustrati i passaggi di base per creare metodi che utilizzano un contratto duplex (bidirezionale).</span><span class="sxs-lookup"><span data-stu-id="b25fe-105">This topic shows the basic steps to create methods that use a duplex (two-way) contract.</span></span> <span data-ttu-id="b25fe-106">Un contratto duplex consente ai client e ai server di comunicare tra loro in modo indipendente, affinché siano entrambi in grado di effettuare chiamate all'altro.</span><span class="sxs-lookup"><span data-stu-id="b25fe-106">A duplex contract allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="b25fe-107">Il contratto duplex è uno dei tre modelli di messaggi disponibili per i servizi Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="b25fe-107">The duplex contract is one of three message patterns available to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="b25fe-108">Gli altri due modelli sono il modello unidirezionale e il modello request/reply.</span><span class="sxs-lookup"><span data-stu-id="b25fe-108">The other two message patterns are one-way and request-reply.</span></span> <span data-ttu-id="b25fe-109">Un contratto duplex è costituito da due contratti unidirezionali tra il client e il server e non richiede che le chiamate al metodo siano correlate.</span><span class="sxs-lookup"><span data-stu-id="b25fe-109">A duplex contract consists of two one-way contracts between the client and the server and does not require that the method calls be correlated.</span></span> <span data-ttu-id="b25fe-110">Utilizzare questo tipo di contratto quando il servizio deve richiedere al client ulteriori informazioni o generare in modo esplicito eventi sul client.</span><span class="sxs-lookup"><span data-stu-id="b25fe-110">Use this kind of contract when your service must query the client for more information or explicitly raise events on the client.</span></span> <span data-ttu-id="b25fe-111">Per ulteriori informazioni sulla creazione di un'applicazione client per un contratto duplex, vedere [procedura: accedere ai servizi con un contratto duplex](how-to-access-services-with-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="b25fe-111">For more information about creating a client application for a duplex contract, see [How to: Access Services with a Duplex Contract](how-to-access-services-with-a-duplex-contract.md).</span></span> <span data-ttu-id="b25fe-112">Per un esempio funzionante, vedere l'esempio [duplex](../samples/duplex.md) .</span><span class="sxs-lookup"><span data-stu-id="b25fe-112">For a working sample, see the [Duplex](../samples/duplex.md) sample.</span></span>  
  
### <a name="to-create-a-duplex-contract"></a><span data-ttu-id="b25fe-113">Per creare un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="b25fe-113">To create a duplex contract</span></span>  
  
1. <span data-ttu-id="b25fe-114">Creare l'interfaccia che rappresenta il lato server del contratto duplex.</span><span class="sxs-lookup"><span data-stu-id="b25fe-114">Create the interface that makes up the server side of the duplex contract.</span></span>  
  
2. <span data-ttu-id="b25fe-115">Applicare la classe <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b25fe-115">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3. <span data-ttu-id="b25fe-116">Dichiarare le firme del metodo nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b25fe-116">Declare the method signatures in the interface.</span></span>  
  
4. <span data-ttu-id="b25fe-117">Applicare la classe <xref:System.ServiceModel.OperationContractAttribute> a ogni firma del metodo che deve essere parte del contratto pubblico.</span><span class="sxs-lookup"><span data-stu-id="b25fe-117">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
5. <span data-ttu-id="b25fe-118">Creare l'interfaccia di callback che definisce il set di operazioni che il servizio può richiamare nel client.</span><span class="sxs-lookup"><span data-stu-id="b25fe-118">Create the callback interface that defines the set of operations that the service can invoke on the client.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6. <span data-ttu-id="b25fe-119">Dichiarare le firme del metodo nell'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="b25fe-119">Declare the method signatures in the callback interface.</span></span>  
  
7. <span data-ttu-id="b25fe-120">Applicare la classe <xref:System.ServiceModel.OperationContractAttribute> a ogni firma del metodo che deve essere parte del contratto pubblico.</span><span class="sxs-lookup"><span data-stu-id="b25fe-120">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
8. <span data-ttu-id="b25fe-121">Collegare le due interfacce in un contratto duplex impostando la proprietà <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> nell'interfaccia primaria sul tipo dell'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="b25fe-121">Link the two interfaces into a duplex contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> property in the primary interface to the type of the callback interface.</span></span>  
  
### <a name="to-call-methods-on-the-client"></a><span data-ttu-id="b25fe-122">Per chiamare i metodi nel client.</span><span class="sxs-lookup"><span data-stu-id="b25fe-122">To call methods on the client</span></span>  
  
1. <span data-ttu-id="b25fe-123">Nell'implementazione del servizio del contratto primario, dichiarare una variabile per l'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="b25fe-123">In the service's implementation of the primary contract, declare a variable for the callback interface.</span></span>  
  
2. <span data-ttu-id="b25fe-124">Impostare la variabile sul riferimento dell'oggetto restituito dal metodo <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> della classe <xref:System.ServiceModel.OperationContext>.</span><span class="sxs-lookup"><span data-stu-id="b25fe-124">Set the variable to the object reference returned by the <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> method of the <xref:System.ServiceModel.OperationContext> class.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3. <span data-ttu-id="b25fe-125">Chiamare i metodi definiti dall'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="b25fe-125">Call the methods defined by the callback interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b25fe-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="b25fe-126">Example</span></span>  
 <span data-ttu-id="b25fe-127">Nell'esempio di codice seguente viene illustrata la comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="b25fe-127">The following code example demonstrates duplex communication.</span></span> <span data-ttu-id="b25fe-128">Il contratto del servizio contiene le operazioni del servizio per spostarsi avanti e indietro.</span><span class="sxs-lookup"><span data-stu-id="b25fe-128">The service’s contract contains service operations for moving forward and backward.</span></span> <span data-ttu-id="b25fe-129">Il contratto del client contiene un'operazione del servizio per segnalare la sua posizione.</span><span class="sxs-lookup"><span data-stu-id="b25fe-129">The client’s contract contains a service operation for reporting its position.</span></span>  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
- <span data-ttu-id="b25fe-130">L'applicazione degli attributi <xref:System.ServiceModel.ServiceContractAttribute> e <xref:System.ServiceModel.OperationContractAttribute> consente di generare automaticamente le definizioni del contratto di servizio nel linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language).</span><span class="sxs-lookup"><span data-stu-id="b25fe-130">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes allows the automatic generation of service contract definitions in the Web Services Description Language (WSDL).</span></span>  
  
- <span data-ttu-id="b25fe-131">Utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per recuperare il documento WSDL e (facoltativo) il codice e la configurazione di un client.</span><span class="sxs-lookup"><span data-stu-id="b25fe-131">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to retrieve the WSDL document and (optional) code and configuration for a client.</span></span>  
  
- <span data-ttu-id="b25fe-132">Gli endpoint che espongono servizi duplex devono essere protetti.</span><span class="sxs-lookup"><span data-stu-id="b25fe-132">Endpoints exposing duplex services must be secured.</span></span> <span data-ttu-id="b25fe-133">Quando un servizio riceve un messaggio duplex, analizza l'elemento ReplyTo contenuto nel messaggio in arrivo per stabilire dove inviare la replica.</span><span class="sxs-lookup"><span data-stu-id="b25fe-133">When a service receives a duplex message, it looks at the ReplyTo in that incoming message to determine where to send the reply.</span></span> <span data-ttu-id="b25fe-134">Se il canale non è protetto, un client non attendibile potrebbe inviare un messaggio dannoso con un elemento ReplyTo del computer di destinazione, il che comporta un Denial of Service (DoS) del computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b25fe-134">If the channel is not secured, then an untrusted client could send a malicious message with a target machine's ReplyTo, leading to a denial of service of the target machine.</span></span> <span data-ttu-id="b25fe-135">Con i messaggi request/reply normali, questo non è un problema, perché ReplyTo viene ignorato e la risposta viene inviata sul canale sul quale è arrivato il messaggio originale.</span><span class="sxs-lookup"><span data-stu-id="b25fe-135">With regular request-reply messages, this is not an issue, because the ReplyTo is ignored and the response is sent on the channel the original message came in on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b25fe-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b25fe-136">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="b25fe-137">Procedura: accedere ai servizi con un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="b25fe-137">How to: Access Services with a Duplex Contract</span></span>](how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="b25fe-138">Duplex</span><span class="sxs-lookup"><span data-stu-id="b25fe-138">Duplex</span></span>](../samples/duplex.md)
- [<span data-ttu-id="b25fe-139">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="b25fe-139">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)
- [<span data-ttu-id="b25fe-140">Procedura: Definire un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="b25fe-140">How to: Define a Service Contract</span></span>](../how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="b25fe-141">Sessione</span><span class="sxs-lookup"><span data-stu-id="b25fe-141">Session</span></span>](../samples/session.md)
