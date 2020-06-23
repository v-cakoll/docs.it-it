---
title: "Procedura: specificare un'associazione al client in codice"
description: Informazioni su come specificare l'associazione per un client WCF in modo imperativo nel codice. Il client accede a un servizio in questo esempio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6bee5da4-adf7-42e6-8f78-63a9e5c6dbad
ms.openlocfilehash: e5e1dff98121985a598579d83043de838e21e5f1
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244504"
---
# <a name="how-to-specify-a-client-binding-in-code"></a><span data-ttu-id="ae5b0-104">Procedura: specificare un'associazione al client in codice</span><span class="sxs-lookup"><span data-stu-id="ae5b0-104">How to: Specify a Client Binding in Code</span></span>
<span data-ttu-id="ae5b0-105">Questo esempio illustra un client creato in modo da utilizzare un servizio di calcolatrice. Inoltre, l'associazione a tale client viene specificata in modo imperativo in codice.</span><span class="sxs-lookup"><span data-stu-id="ae5b0-105">In this example, a client is created to use a calculator service and the binding for that client is specified imperatively in code.</span></span> <span data-ttu-id="ae5b0-106">Il client accede al servizio `CalculatorService` che implementa l'interfaccia `ICalculator`. Sia il servizio sia il client utilizzano la classe <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="ae5b0-106">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="ae5b0-107">Questa procedura presuppone che il servizio di calcolatrice sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ae5b0-107">This procedure assumes that the calculator service is running.</span></span> <span data-ttu-id="ae5b0-108">Per informazioni sulla compilazione del servizio, vedere [procedura: specificare un'associazione al servizio nella configurazione](how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="ae5b0-108">For information about building the service, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="ae5b0-109">USA inoltre lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) fornisce per generare automaticamente i componenti client.</span><span class="sxs-lookup"><span data-stu-id="ae5b0-109">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="ae5b0-110">Lo strumento genera il codice client di accesso al servizio.</span><span class="sxs-lookup"><span data-stu-id="ae5b0-110">The tool generates the client code for accessing the service.</span></span>  
  
 <span data-ttu-id="ae5b0-111">Il client viene compilato in due parti.</span><span class="sxs-lookup"><span data-stu-id="ae5b0-111">The client is built in two parts.</span></span> <span data-ttu-id="ae5b0-112">Lo strumento Svcutil.exe genera la classe `ClientCalculator` che implementa l'interfaccia `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="ae5b0-112">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="ae5b0-113">Questa applicazione client viene quindi costruita creando un'istanza della classe `ClientCalculator` e specificando in codice l'associazione e l'indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="ae5b0-113">This client application is then constructed by constructing an instance of `ClientCalculator` and then specifying the binding and the address for the service in code.</span></span>  
  
 <span data-ttu-id="ae5b0-114">Per la copia di origine di questo esempio, vedere l'esempio di [base](./samples/basicbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ae5b0-114">For the source copy of this example, see the [BasicBinding](./samples/basicbinding.md) sample.</span></span>  
  
### <a name="to-specify-a-custom-binding-in-code"></a><span data-ttu-id="ae5b0-115">Per specificare in codice un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="ae5b0-115">To specify a custom binding in code</span></span>  
  
1. <span data-ttu-id="ae5b0-116">Utilizzare Svcutil.exe dalla riga di comando per generare il codice da metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="ae5b0-116">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. <span data-ttu-id="ae5b0-117">Il client generato contiene l'interfaccia `ICalculator` che definisce il contratto di servizio che l'implementazione del client deve soddisfare.</span><span class="sxs-lookup"><span data-stu-id="ae5b0-117">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#1)]
     [!code-vb[C_HowTo_CodeClientBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#1)]  
  
3. <span data-ttu-id="ae5b0-118">Il client generato contiene inoltre l'implementazione della classe `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="ae5b0-118">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#2)]
     [!code-vb[C_HowTo_CodeClientBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#2)]  
  
4. <span data-ttu-id="ae5b0-119">Creare un'istanza della classe `ClientCalculator` che utilizza la classe <xref:System.ServiceModel.BasicHttpBinding> in un'applicazione client e quindi chiamare le operazioni del servizio all'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="ae5b0-119">Create an instance of the `ClientCalculator` that uses the <xref:System.ServiceModel.BasicHttpBinding> class in a client application, and then call the service operations at the specified address.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#3)]
     [!code-vb[C_HowTo_CodeClientBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#3)]  
  
5. <span data-ttu-id="ae5b0-120">Compilare ed eseguire il client.</span><span class="sxs-lookup"><span data-stu-id="ae5b0-120">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae5b0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae5b0-121">See also</span></span>

- [<span data-ttu-id="ae5b0-122">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="ae5b0-122">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
