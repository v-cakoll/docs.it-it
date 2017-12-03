---
title: 'Procedura: accedere ai servizi con un contratto duplex'
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
helpviewer_keywords: duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ec8b7f37dc7f04a7ddb2c6373b50e98fe41cf98
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-access-services-with-a-duplex-contract"></a><span data-ttu-id="185c0-102">Procedura: accedere ai servizi con un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="185c0-102">How to: Access Services with a Duplex Contract</span></span>
<span data-ttu-id="185c0-103">Una funzionalità di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è la possibilità di creare un servizio che utilizza un modello di messaggistica duplex.</span><span class="sxs-lookup"><span data-stu-id="185c0-103">One feature of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is the ability to create a service that uses a duplex messaging pattern.</span></span> <span data-ttu-id="185c0-104">Questo modello consente a un servizio di comunicare con il client tramite un callback.</span><span class="sxs-lookup"><span data-stu-id="185c0-104">This pattern allows a service to communicate with the client through a callback.</span></span> <span data-ttu-id="185c0-105">In questo argomento vengono illustrati i passaggi per creare un client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in una classe client che implementa l'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="185c0-105">This topic shows the steps to create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client in a client class that implements the callback interface.</span></span>  
  
 <span data-ttu-id="185c0-106">Un'associazione duale espone l'indirizzo IP del client al servizio.</span><span class="sxs-lookup"><span data-stu-id="185c0-106">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="185c0-107">Nel client è necessario implementare un meccanismo di sicurezza in grado di garantire che il client si connetta solo a servizi ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="185c0-107">The client should use security to ensure that it connects only to services it trusts.</span></span>  
  
 <span data-ttu-id="185c0-108">Per un'esercitazione sulla creazione di base [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servizio e client, vedere [esercitazione introduttiva](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="185c0-108">For a tutorial on creating a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service and client, see [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
### <a name="to-access-a-duplex-service"></a><span data-ttu-id="185c0-109">Per accedere a un servizio duplex</span><span class="sxs-lookup"><span data-stu-id="185c0-109">To access a duplex service</span></span>  
  
1.  <span data-ttu-id="185c0-110">Creare un servizio che contiene due interfacce.</span><span class="sxs-lookup"><span data-stu-id="185c0-110">Create a service that contains two interfaces.</span></span> <span data-ttu-id="185c0-111">La prima interfaccia è per il servizio, la seconda è per il callback.</span><span class="sxs-lookup"><span data-stu-id="185c0-111">The first interface is for the service, the second is for the callback.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="185c0-112">creazione di un servizio duplex, vedere [procedura: creare un contratto Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="185c0-112"> creating a duplex service, see [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
2.  <span data-ttu-id="185c0-113">Eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="185c0-113">Run the service.</span></span>  
  
3.  <span data-ttu-id="185c0-114">Utilizzare il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare contratti (interfacce) per il client.</span><span class="sxs-lookup"><span data-stu-id="185c0-114">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate contracts (interfaces) for the client.</span></span> <span data-ttu-id="185c0-115">Per informazioni su come eseguire questa operazione, vedere [procedura: creare un Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="185c0-115">For information about how to do this, see  [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
4.  <span data-ttu-id="185c0-116">Implementare l'interfaccia di callback nella classe client, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="185c0-116">Implement the callback interface in the client class, as shown in the following example.</span></span>  
  
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
  
5.  <span data-ttu-id="185c0-117">Creare un'istanza della classe <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="185c0-117">Create an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="185c0-118">Il costruttore richiede un'istanza della classe client.</span><span class="sxs-lookup"><span data-stu-id="185c0-118">The constructor requires an instance of the client class.</span></span>  
  
    ```csharp  
    InstanceContext site = new InstanceContext(new CallbackHandler());  
    ```  
  
    ```vb  
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())  
    ```  
  
6.  <span data-ttu-id="185c0-119">Creare un'istanza del client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizzando il costruttore che richiede un oggetto <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="185c0-119">Create an instance of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client using the constructor that requires an <xref:System.ServiceModel.InstanceContext> object.</span></span> <span data-ttu-id="185c0-120">Il secondo parametro del costruttore è il nome di un endpoint contenuto nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="185c0-120">The second parameter of the constructor is the name of an endpoint found in the configuration file.</span></span>  
  
    ```csharp  
    CalculatorDuplexClient wcfClient =   
    new CalculatorDuplexClient(site, "default")  
    ```  
  
    ```vb  
    Dim wcfClient As New CalculatorDuplexClient(site, "default")  
    ```  
  
7.  <span data-ttu-id="185c0-121">Chiamare i metodi del client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] secondo le esigenze.</span><span class="sxs-lookup"><span data-stu-id="185c0-121">Call the methods of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client as required.</span></span>  
  
## <a name="example"></a><span data-ttu-id="185c0-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="185c0-122">Example</span></span>  
 <span data-ttu-id="185c0-123">Nell'esempio di codice seguente viene descritto come creare una classe client che accede a un contratto duplex.</span><span class="sxs-lookup"><span data-stu-id="185c0-123">The following code example demonstrates how to create a client class that accesses a duplex contract.</span></span>  
  
 [!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
 [!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="185c0-124">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="185c0-124">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="185c0-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="185c0-125">See Also</span></span>  
 [<span data-ttu-id="185c0-126">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="185c0-126">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="185c0-127">Procedura: creare un contratto Duplex</span><span class="sxs-lookup"><span data-stu-id="185c0-127">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="185c0-128">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="185c0-128">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="185c0-129">Procedura: Creare un client</span><span class="sxs-lookup"><span data-stu-id="185c0-129">How to: Create a Client</span></span>](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="185c0-130">Procedura: usare ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="185c0-130">How to: Use the ChannelFactory</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
