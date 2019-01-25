---
title: 'Procedura: Servizi di accesso con un contratto duplex'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: 2f83b8ac71bfc53791f7de42d127badbda0d3881
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610312"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a><span data-ttu-id="96f7e-102">Procedura: Servizi di accesso con un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="96f7e-102">How to: Access services with a duplex contract</span></span>

<span data-ttu-id="96f7e-103">Una funzionalità di Windows Communication Foundation (WCF) è la possibilità di creare un servizio che usa un modello di messaggistica duplex.</span><span class="sxs-lookup"><span data-stu-id="96f7e-103">One feature of Windows Communication Foundation (WCF) is the ability to create a service that uses a duplex messaging pattern.</span></span> <span data-ttu-id="96f7e-104">Questo modello consente a un servizio di comunicare con il client tramite un callback.</span><span class="sxs-lookup"><span data-stu-id="96f7e-104">This pattern allows a service to communicate with the client through a callback.</span></span> <span data-ttu-id="96f7e-105">Questo argomento illustra i passaggi per creare un client WCF in una classe client che implementa l'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="96f7e-105">This topic shows the steps to create a WCF client in a client class that implements the callback interface.</span></span>

<span data-ttu-id="96f7e-106">Un'associazione duale espone l'indirizzo IP del client al servizio.</span><span class="sxs-lookup"><span data-stu-id="96f7e-106">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="96f7e-107">Nel client è necessario implementare un meccanismo di sicurezza in grado di garantire che il client si connetta solo a servizi ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="96f7e-107">The client should use security to ensure that it connects only to services it trusts.</span></span>

<span data-ttu-id="96f7e-108">Per un'esercitazione sulla creazione di un servizio WCF di base e un client, vedere [esercitazione introduttiva](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="96f7e-108">For a tutorial on creating a basic WCF service and client, see [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>

## <a name="to-access-a-duplex-service"></a><span data-ttu-id="96f7e-109">Per accedere a un servizio duplex</span><span class="sxs-lookup"><span data-stu-id="96f7e-109">To access a duplex service</span></span>

1. <span data-ttu-id="96f7e-110">Creare un servizio che contiene due interfacce.</span><span class="sxs-lookup"><span data-stu-id="96f7e-110">Create a service that contains two interfaces.</span></span> <span data-ttu-id="96f7e-111">La prima interfaccia è per il servizio, la seconda è per il callback.</span><span class="sxs-lookup"><span data-stu-id="96f7e-111">The first interface is for the service, the second is for the callback.</span></span> <span data-ttu-id="96f7e-112">Per altre informazioni sulla creazione di un servizio duplex, vedere [come: Creare un contratto Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="96f7e-112">For more information about creating a duplex service, see [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>

2. <span data-ttu-id="96f7e-113">Eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="96f7e-113">Run the service.</span></span>

3. <span data-ttu-id="96f7e-114">Usare la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare contratti (interfacce) per il client.</span><span class="sxs-lookup"><span data-stu-id="96f7e-114">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate contracts (interfaces) for the client.</span></span> <span data-ttu-id="96f7e-115">Per informazioni su come eseguire questa operazione, vedere [come: Creare un Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="96f7e-115">For information about how to do this, see  [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>

4. <span data-ttu-id="96f7e-116">Implementare l'interfaccia di callback nella classe client, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="96f7e-116">Implement the callback interface in the client class, as shown in the following example.</span></span>

    ```csharp
    public class CallbackHandler : ICalculatorDuplexCallback
    {
        public void Result(double result)
        {
            Console.WriteLine("Result ({0})", result);
        }
        public void Equation(string equation)
        {
            Console.WriteLine("Equation({0})", equation);
        }
    }
    ```

    ```vb
    Public Class CallbackHandler
    Implements ICalculatorDuplexCallback
       Public Sub Result (ByVal result As Double)
          Console.WriteLine("Result ({0})", result)
       End Sub
        Public Sub Equation(ByVal equation As String)
            Console.Writeline("Equation({0})", equation)
        End Sub
    End Class
    ```

5. <span data-ttu-id="96f7e-117">Creare un'istanza della classe <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="96f7e-117">Create an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="96f7e-118">Il costruttore richiede un'istanza della classe client.</span><span class="sxs-lookup"><span data-stu-id="96f7e-118">The constructor requires an instance of the client class.</span></span>

    ```csharp
    InstanceContext site = new InstanceContext(new CallbackHandler());
    ```

    ```vb
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())
    ```

6. <span data-ttu-id="96f7e-119">Creare un'istanza del client WCF usando il costruttore che richiede un <xref:System.ServiceModel.InstanceContext> oggetto.</span><span class="sxs-lookup"><span data-stu-id="96f7e-119">Create an instance of the WCF client using the constructor that requires an <xref:System.ServiceModel.InstanceContext> object.</span></span> <span data-ttu-id="96f7e-120">Il secondo parametro del costruttore è il nome di un endpoint contenuto nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="96f7e-120">The second parameter of the constructor is the name of an endpoint found in the configuration file.</span></span>

    ```csharp
    CalculatorDuplexClient wcfClient = new CalculatorDuplexClient(site, "default");
    ```

    ```vb
    Dim wcfClient As New CalculatorDuplexClient(site, "default")
    ```

7. <span data-ttu-id="96f7e-121">Chiamare i metodi del client WCF in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="96f7e-121">Call the methods of the WCF client as required.</span></span>

## <a name="example"></a><span data-ttu-id="96f7e-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="96f7e-122">Example</span></span>

<span data-ttu-id="96f7e-123">Nell'esempio di codice seguente viene descritto come creare una classe client che accede a un contratto duplex.</span><span class="sxs-lookup"><span data-stu-id="96f7e-123">The following code example demonstrates how to create a client class that accesses a duplex contract.</span></span>

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a><span data-ttu-id="96f7e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96f7e-124">See also</span></span>

- [<span data-ttu-id="96f7e-125">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="96f7e-125">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)
- [<span data-ttu-id="96f7e-126">Procedura: Creare un contratto Duplex</span><span class="sxs-lookup"><span data-stu-id="96f7e-126">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="96f7e-127">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="96f7e-127">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="96f7e-128">Procedura: Creare un Client</span><span class="sxs-lookup"><span data-stu-id="96f7e-128">How to: Create a Client</span></span>](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="96f7e-129">Procedura: Usare ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="96f7e-129">How to: Use the ChannelFactory</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
