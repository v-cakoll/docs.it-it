---
title: 'Procedura: accedere ai servizi con un contratto duplex'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: bc42792b827b49265a0b1addf959de2fa1a041e3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597215"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a><span data-ttu-id="6ef71-102">Procedura: accedere ai servizi con un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="6ef71-102">How to: Access services with a duplex contract</span></span>

<span data-ttu-id="6ef71-103">Una funzionalità di Windows Communication Foundation (WCF) è la possibilità di creare un servizio che usa un modello di messaggistica duplex.</span><span class="sxs-lookup"><span data-stu-id="6ef71-103">One feature of Windows Communication Foundation (WCF) is the ability to create a service that uses a duplex messaging pattern.</span></span> <span data-ttu-id="6ef71-104">Questo modello consente a un servizio di comunicare con il client tramite un callback.</span><span class="sxs-lookup"><span data-stu-id="6ef71-104">This pattern allows a service to communicate with the client through a callback.</span></span> <span data-ttu-id="6ef71-105">In questo argomento vengono illustrati i passaggi per creare un client WCF in una classe client che implementa l'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="6ef71-105">This topic shows the steps to create a WCF client in a client class that implements the callback interface.</span></span>

<span data-ttu-id="6ef71-106">Un'associazione duale espone l'indirizzo IP del client al servizio.</span><span class="sxs-lookup"><span data-stu-id="6ef71-106">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="6ef71-107">Nel client è necessario implementare un meccanismo di sicurezza in grado di garantire che il client si connetta solo a servizi ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="6ef71-107">The client should use security to ensure that it connects only to services it trusts.</span></span>

<span data-ttu-id="6ef71-108">Per un'esercitazione sulla creazione di un servizio e un client WCF di base, vedere [Introduzione esercitazione](../getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="6ef71-108">For a tutorial on creating a basic WCF service and client, see [Getting Started Tutorial](../getting-started-tutorial.md).</span></span>

## <a name="to-access-a-duplex-service"></a><span data-ttu-id="6ef71-109">Per accedere a un servizio duplex</span><span class="sxs-lookup"><span data-stu-id="6ef71-109">To access a duplex service</span></span>

1. <span data-ttu-id="6ef71-110">Creare un servizio che contiene due interfacce.</span><span class="sxs-lookup"><span data-stu-id="6ef71-110">Create a service that contains two interfaces.</span></span> <span data-ttu-id="6ef71-111">La prima interfaccia è per il servizio, la seconda è per il callback.</span><span class="sxs-lookup"><span data-stu-id="6ef71-111">The first interface is for the service, the second is for the callback.</span></span> <span data-ttu-id="6ef71-112">Per ulteriori informazioni sulla creazione di un servizio duplex, vedere [procedura: creare un contratto duplex](how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="6ef71-112">For more information about creating a duplex service, see [How to: Create a Duplex Contract](how-to-create-a-duplex-contract.md).</span></span>

2. <span data-ttu-id="6ef71-113">Eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="6ef71-113">Run the service.</span></span>

3. <span data-ttu-id="6ef71-114">Utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per generare contratti (interfacce) per il client.</span><span class="sxs-lookup"><span data-stu-id="6ef71-114">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate contracts (interfaces) for the client.</span></span> <span data-ttu-id="6ef71-115">Per informazioni su come eseguire questa operazione, vedere [How to: Create a client](../how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="6ef71-115">For information about how to do this, see  [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>

4. <span data-ttu-id="6ef71-116">Implementare l'interfaccia di callback nella classe client, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6ef71-116">Implement the callback interface in the client class, as shown in the following example.</span></span>

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
            Console.WriteLine("Equation({0})", equation)
        End Sub
    End Class
    ```

5. <span data-ttu-id="6ef71-117">Creare un'istanza della classe <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="6ef71-117">Create an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="6ef71-118">Il costruttore richiede un'istanza della classe client.</span><span class="sxs-lookup"><span data-stu-id="6ef71-118">The constructor requires an instance of the client class.</span></span>

    ```csharp
    InstanceContext site = new InstanceContext(new CallbackHandler());
    ```

    ```vb
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())
    ```

6. <span data-ttu-id="6ef71-119">Creare un'istanza del client WCF utilizzando il costruttore che richiede un <xref:System.ServiceModel.InstanceContext> oggetto.</span><span class="sxs-lookup"><span data-stu-id="6ef71-119">Create an instance of the WCF client using the constructor that requires an <xref:System.ServiceModel.InstanceContext> object.</span></span> <span data-ttu-id="6ef71-120">Il secondo parametro del costruttore è il nome di un endpoint contenuto nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6ef71-120">The second parameter of the constructor is the name of an endpoint found in the configuration file.</span></span>

    ```csharp
    CalculatorDuplexClient wcfClient = new CalculatorDuplexClient(site, "default");
    ```

    ```vb
    Dim wcfClient As New CalculatorDuplexClient(site, "default")
    ```

7. <span data-ttu-id="6ef71-121">Chiamare i metodi del client WCF come richiesto.</span><span class="sxs-lookup"><span data-stu-id="6ef71-121">Call the methods of the WCF client as required.</span></span>

## <a name="example"></a><span data-ttu-id="6ef71-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="6ef71-122">Example</span></span>

<span data-ttu-id="6ef71-123">Nell'esempio di codice seguente viene descritto come creare una classe client che accede a un contratto duplex.</span><span class="sxs-lookup"><span data-stu-id="6ef71-123">The following code example demonstrates how to create a client class that accesses a duplex contract.</span></span>

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a><span data-ttu-id="6ef71-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ef71-124">See also</span></span>

- [<span data-ttu-id="6ef71-125">Esercitazione Introduzione</span><span class="sxs-lookup"><span data-stu-id="6ef71-125">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)
- [<span data-ttu-id="6ef71-126">Procedura: creare un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="6ef71-126">How to: Create a Duplex Contract</span></span>](how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="6ef71-127">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="6ef71-127">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="6ef71-128">Procedura: Creare un client</span><span class="sxs-lookup"><span data-stu-id="6ef71-128">How to: Create a Client</span></span>](../how-to-create-a-wcf-client.md)
- [<span data-ttu-id="6ef71-129">Procedura: usare ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="6ef71-129">How to: Use the ChannelFactory</span></span>](how-to-use-the-channelfactory.md)
