---
title: "Procedura: specificare un'associazione client nella configurazione"
description: Informazioni su come specificare in modo dichiarativo l'associazione per un client WCF in un file di configurazione. Il client accede a un servizio in questo esempio.
ms.date: 03/30/2017
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
ms.openlocfilehash: 28778b6ae853199c5d7943f329bb087760f4bb11
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244491"
---
# <a name="how-to-specify-a-client-binding-in-configuration"></a><span data-ttu-id="34335-104">Procedura: specificare un'associazione client nella configurazione</span><span class="sxs-lookup"><span data-stu-id="34335-104">How to: Specify a Client Binding in Configuration</span></span>
<span data-ttu-id="34335-105">In questo esempio, viene creata un'applicazione console client per utilizzare un servizio calcolatrice e nella configurazione viene spiegata in modo dichiarativo l'associazione per quel client.</span><span class="sxs-lookup"><span data-stu-id="34335-105">In this example, a client console application is created to use a calculator service, and the binding for that client is specified declaratively in configuration.</span></span> <span data-ttu-id="34335-106">Il client accede al servizio `CalculatorService` che implementa l'interfaccia `ICalculator`. Sia il servizio sia il client utilizzano la classe <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="34335-106">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="34335-107">Nella procedura illustrata si presuppone che il servizio calcolatrice sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="34335-107">The procedure outlined assumes that the calculator service is running.</span></span> <span data-ttu-id="34335-108">Per informazioni su come compilare il servizio, vedere [procedura: specificare un'associazione al servizio nella configurazione](how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="34335-108">For information about how to build the service, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="34335-109">Viene inoltre utilizzato lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) fornito da Windows Communication Foundation (WCF) per generare automaticamente i componenti client.</span><span class="sxs-lookup"><span data-stu-id="34335-109">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) that Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="34335-110">Lo strumento genera il codice e la configurazione client per l'accesso al servizio.</span><span class="sxs-lookup"><span data-stu-id="34335-110">The tool generates the client code and configuration for accessing the service.</span></span>  
  
 <span data-ttu-id="34335-111">Il client viene compilato in due parti.</span><span class="sxs-lookup"><span data-stu-id="34335-111">The client is built in two parts.</span></span> <span data-ttu-id="34335-112">Lo strumento Svcutil.exe genera la classe `ClientCalculator` che implementa l'interfaccia `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="34335-112">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="34335-113">Questa applicazione client viene quindi costruita creando un'istanza di `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="34335-113">This client application is then constructed by constructing an instance of `ClientCalculator`.</span></span>  
  
 <span data-ttu-id="34335-114">La procedura solitamente consigliata consiste nello specificare in modo dichiarativo l'associazione e le informazioni dell'indirizzo nella configurazione anziché in modo imperativo nel codice.</span><span class="sxs-lookup"><span data-stu-id="34335-114">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="34335-115">In genere definire endpoint nel codice non è pratico in quanto le associazioni e gli indirizzi di un servizio distribuito sono solitamente diversi da quelli usati durante lo sviluppo del servizio.</span><span class="sxs-lookup"><span data-stu-id="34335-115">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="34335-116">Più in generale, se le informazioni su associazione e indirizzo non vengono incluse nel codice, tali dati possono essere modificati senza dover compilare o distribuire nuovamente l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="34335-116">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="34335-117">È possibile eseguire tutti i passaggi di configurazione seguenti utilizzando lo [strumento Editor di configurazione (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="34335-117">You can perform all of the following configuration steps by using the [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="34335-118">Per la copia di origine di questo esempio, vedere l'esempio di [base](./samples/basicbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="34335-118">For the source copy of this example, see the [BasicBinding](./samples/basicbinding.md) sample.</span></span>  
  
### <a name="specifying-a-client-binding-in-configuration"></a><span data-ttu-id="34335-119">Specifica di un'associazione client nella configurazione</span><span class="sxs-lookup"><span data-stu-id="34335-119">Specifying a client binding in configuration</span></span>  
  
1. <span data-ttu-id="34335-120">Utilizzare Svcutil.exe dalla riga di comando per generare il codice da metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="34335-120">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. <span data-ttu-id="34335-121">Il client generato contiene l'interfaccia `ICalculator` che definisce il contratto di servizio che l'implementazione del client deve soddisfare.</span><span class="sxs-lookup"><span data-stu-id="34335-121">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3. <span data-ttu-id="34335-122">Il client generato contiene inoltre l'implementazione della classe `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="34335-122">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4. <span data-ttu-id="34335-123">Svcutil.exe genera inoltre la configurazione per il client che utilizza la classe <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="34335-123">Svcutil.exe also generates the configuration for the client that uses the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span> <span data-ttu-id="34335-124">Quando si usa Visual Studio, assegnare un nome al file App.config. Si noti che le informazioni sull'indirizzo e sull'associazione non sono specificate in un punto qualsiasi all'interno dell'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="34335-124">When using Visual Studio, name this file App.config. Note that the address and binding information are not specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="34335-125">Non è necessario, inoltre, scrivere codice per recuperarle dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="34335-125">Also, code does not have to be written to retrieve that information from the configuration file.</span></span>  
  
     [!code-xml[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]

5. <span data-ttu-id="34335-126">Creare un'istanza di `ClientCalculator` in un'applicazione, quindi chiamare le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="34335-126">Create an instance of the `ClientCalculator` in an application, and then call the service operations.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6. <span data-ttu-id="34335-127">Compilare ed eseguire il client.</span><span class="sxs-lookup"><span data-stu-id="34335-127">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34335-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34335-128">See also</span></span>

- [<span data-ttu-id="34335-129">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="34335-129">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
