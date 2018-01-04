---
title: 'Procedura: dichiarare errori nei contratti di servizio'
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
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bcf707e58586673097c89e0e0f4d72ea68ef7247
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-declare-faults-in-service-contracts"></a><span data-ttu-id="b836b-102">Procedura: dichiarare errori nei contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="b836b-102">How to: Declare Faults in Service Contracts</span></span>
<span data-ttu-id="b836b-103">Nel codice gestito, vengono generate eccezioni quando si verificano condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="b836b-103">In managed code, exceptions are thrown when error conditions occur.</span></span> <span data-ttu-id="b836b-104">Nelle applicazioni [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], tuttavia, i contratti di servizio specificano quali informazioni sugli errori vengono restituite dai client dichiarando errori SOAP nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="b836b-104">In [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] applications, however, service contracts specify what error information is returned to clients by declaring SOAP faults in the service contract.</span></span> <span data-ttu-id="b836b-105">Per una panoramica della relazione tra eccezioni ed errori, vedere [specifica e gestione degli errori in contratti e servizi](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span><span class="sxs-lookup"><span data-stu-id="b836b-105">For an overview of the relationship between exceptions and faults, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
### <a name="create-a-service-contract-that-specifies-a-soap-fault"></a><span data-ttu-id="b836b-106">Creare un contratto di servizio che specifica un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="b836b-106">Create a service contract that specifies a SOAP fault</span></span>  
  
1.  <span data-ttu-id="b836b-107">Creare un contratto di servizio che contiene almeno un'operazione.</span><span class="sxs-lookup"><span data-stu-id="b836b-107">Create a service contract that contains at least one operation.</span></span> <span data-ttu-id="b836b-108">Per un esempio, vedere [procedura: definire un contratto di servizio](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="b836b-108">For an example, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2.  <span data-ttu-id="b836b-109">Selezionare un'operazione che può specificare una condizione di errore in merito alla quale i client prevedono di ricevere una notifica.</span><span class="sxs-lookup"><span data-stu-id="b836b-109">Select an operation that can specify an error condition about which clients can expect to be notified.</span></span> <span data-ttu-id="b836b-110">Per decidere quali condizioni di errore giustificano la restituzione di errori SOAP ai client, vedere [specifica e gestione degli errori in contratti e servizi](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span><span class="sxs-lookup"><span data-stu-id="b836b-110">To decide which error conditions justify returning SOAP faults to clients, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
3.  <span data-ttu-id="b836b-111">Applicare una classe <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> all'operazione selezionata e passare un tipo di errore serializzabile al costruttore.</span><span class="sxs-lookup"><span data-stu-id="b836b-111">Apply a <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> to the selected operation and pass a serializable fault type to the constructor.</span></span> <span data-ttu-id="b836b-112">Per informazioni dettagliate sulla creazione e utilizzo di tipi serializzabili, vedere [specifica di trasferimento dei dati nei contratti di servizio](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="b836b-112">For details about creating and using serializable types, see [Specifying Data Transfer in Service Contracts](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).</span></span> <span data-ttu-id="b836b-113">Nell'esempio seguente viene illustrato come specificare che l'operazione `SampleMethod` può produrre un `GreetingFault`.</span><span class="sxs-lookup"><span data-stu-id="b836b-113">The following example shows how to specify that the `SampleMethod` operation can result in a `GreetingFault`.</span></span>  
  
     [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
4.  <span data-ttu-id="b836b-114">Ripetere i passaggi 2 e 3 per tutte le operazioni nel contratto che comunicano condizioni di errore ai client.</span><span class="sxs-lookup"><span data-stu-id="b836b-114">Repeat steps 2 and 3 for all operations in the contract that communicate error conditions to clients.</span></span>  
  
## <a name="implementing-an-operation-to-return-a-specified-soap-fault"></a><span data-ttu-id="b836b-115">Implementazione di un'operazione per restituire un errore SOAP specificato</span><span class="sxs-lookup"><span data-stu-id="b836b-115">Implementing an Operation to Return a Specified SOAP Fault</span></span>  
 <span data-ttu-id="b836b-116">Dopo che un'operazione ha specificato che può essere restituito un determinato errore SOAP (come nella procedura seguente), per comunicare una condizione di errore a un'applicazione chiamante, il passaggio successivo consiste nell'implementare la specifica in questione.</span><span class="sxs-lookup"><span data-stu-id="b836b-116">Once an operation has specified that a specific SOAP fault can be returned (such as in the preceding procedure) to communicate an error condition to a calling application, the next step is to implement that specification.</span></span>  
  
#### <a name="throw-the-specified-soap-fault-in-the-operation"></a><span data-ttu-id="b836b-117">Generare l'errore SOAP specificato nell'operazione</span><span class="sxs-lookup"><span data-stu-id="b836b-117">Throw the specified SOAP fault in the operation</span></span>  
  
1.  <span data-ttu-id="b836b-118">Quando in un'operazione si verifica una condizione di errore specificata da <xref:System.ServiceModel.FaultContractAttribute>, generare una nuova eccezione <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> in cui l'errore SOAP specificato è il parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="b836b-118">When a <xref:System.ServiceModel.FaultContractAttribute>-specified error condition occurs in an operation, throw a new <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> where the specified SOAP fault is the type parameter.</span></span> <span data-ttu-id="b836b-119">Nell'esempio seguente viene illustrato come generare il `GreetingFault` nel `SampleMethod` descritto nella procedura precedente e nella sezione Codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b836b-119">The following example shows how to throw the `GreetingFault` in the `SampleMethod` shown in the preceding procedure and in the following Code section.</span></span>  
  
     [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="b836b-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="b836b-120">Example</span></span>  
 <span data-ttu-id="b836b-121">Nell'esempio di codice seguente viene illustrata un'implementazione di una singola operazione che specifica un `GreetingFault` per l'operazione `SampleMethod`.</span><span class="sxs-lookup"><span data-stu-id="b836b-121">The following code example shows an implementation of a single operation that specifies a `GreetingFault` for the `SampleMethod` operation.</span></span>  
  
 [!code-csharp[FaultContractAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
 [!code-vb[FaultContractAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b836b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b836b-122">See Also</span></span>  
 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>  
 <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
