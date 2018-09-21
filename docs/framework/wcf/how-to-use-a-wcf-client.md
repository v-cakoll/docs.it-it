---
title: 'Procedura: usare un client di Windows Communication Foundation'
ms.date: 09/14/2018
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 12e911fb899cb85121c129b762828cdda01e64f1
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46532584"
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a><span data-ttu-id="03b5e-102">Procedura: usare un client di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="03b5e-102">How to: Use a Windows Communication Foundation Client</span></span>

<span data-ttu-id="03b5e-103">Questa è l'ultima delle sei attività necessarie per creare un'applicazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="03b5e-103">This is the last of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="03b5e-104">Per una panoramica di tutte e sei le attività, vedere l'argomento [Esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="03b5e-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="03b5e-105">Una volta che un proxy di Windows Communication Foundation (WCF) è stato creato e configurato, è possibile creare un'istanza di client e l'applicazione client può essere compilato e usato per comunicare con il servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="03b5e-105">Once a Windows Communication Foundation (WCF) proxy has been created and configured, a client instance can be created and the client application can be compiled and used to communicate with the WCF service.</span></span> <span data-ttu-id="03b5e-106">Questo argomento descrive le procedure per la creazione di istanze e tramite client WCF.</span><span class="sxs-lookup"><span data-stu-id="03b5e-106">This topic describes procedures for instantiating and using a WCF client.</span></span> <span data-ttu-id="03b5e-107">La procedura consente di eseguire tre operazioni:</span><span class="sxs-lookup"><span data-stu-id="03b5e-107">This procedure does three things:</span></span>

1.  <span data-ttu-id="03b5e-108">Crea un'istanza di un client WCF.</span><span class="sxs-lookup"><span data-stu-id="03b5e-108">Instantiates a WCF client.</span></span>

2.  <span data-ttu-id="03b5e-109">Chiamata delle operazioni del servizio dal proxy generato.</span><span class="sxs-lookup"><span data-stu-id="03b5e-109">Calls the service operations from the generated proxy.</span></span>

3.  <span data-ttu-id="03b5e-110">Chiusura del client dopo il completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="03b5e-110">Closes the client once the operation call is completed.</span></span>

## <a name="use-a-windows-communication-foundation-client"></a><span data-ttu-id="03b5e-111">Usare un client Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="03b5e-111">Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="03b5e-112">Aprire il file Program.cs o Program.vb dal progetto GettingStartedClient e sostituire il codice esistente con quello seguente:</span><span class="sxs-lookup"><span data-stu-id="03b5e-112">Open the Program.cs or Program.vb file from the GettingStartedClient project and replace the existing code with the following code:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using GettingStartedClient.ServiceReference1;

namespace GettingStartedClient
{
    class Program
    {
        static void Main(string[] args)
        {
            //Step 1: Create an instance of the WCF proxy.
            CalculatorClient client = new CalculatorClient();

            // Step 2: Call the service operations.
            // Call the Add service operation.
            double value1 = 100.00D;
            double value2 = 15.99D;
            double result = client.Add(value1, value2);
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

            // Call the Subtract service operation.
            value1 = 145.00D;
            value2 = 76.54D;
            result = client.Subtract(value1, value2);
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

            // Call the Multiply service operation.
            value1 = 9.00D;
            value2 = 81.25D;
            result = client.Multiply(value1, value2);
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

            // Call the Divide service operation.
            value1 = 22.00D;
            value2 = 7.00D;
            result = client.Divide(value1, value2);
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

            //Step 3: Closing the client gracefully closes the connection and cleans up resources.
            client.Close();
        }
    }
}
```

```vb
Imports System
Imports System.Collections.Generic
Imports System.Text
Imports System.ServiceModel
Imports GettingStartedClientVB2.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy
        Dim Client As New CalculatorClient()

        'Step 2: Call the service operations.
        'Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        'Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        'Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        'Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Closing the client gracefully closes the connection and cleans up resources.
        Client.Close()

        Console.WriteLine()
        Console.WriteLine("Press <ENTER> to terminate client.")
        Console.ReadLine()

    End Sub

End Module
```

<span data-ttu-id="03b5e-113">Si noti che il `using` oppure `Imports` istruzione che importa il `GettingStartedClient.ServiceReference1`.</span><span class="sxs-lookup"><span data-stu-id="03b5e-113">Notice the `using` or `Imports` statement that imports the `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="03b5e-114">Questo modo viene importato il codice generato dallo **Aggiungi riferimento al servizio** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="03b5e-114">This imports the code generated by **Add Service Reference** in Visual Studio.</span></span> <span data-ttu-id="03b5e-115">Il codice crea un'istanza del proxy WCF e quindi chiama ognuno delle operazioni del servizio esposte dal servizio di calcolatrice, chiude il proxy e termina.</span><span class="sxs-lookup"><span data-stu-id="03b5e-115">The code instantiates the WCF proxy and then calls each of the service operations exposed by the calculator service, closes the proxy, and terminates.</span></span>

<span data-ttu-id="03b5e-116">L'esercitazione è ora completata.</span><span class="sxs-lookup"><span data-stu-id="03b5e-116">You have now completed the tutorial.</span></span> <span data-ttu-id="03b5e-117">È stato definito e implementato un contratto di servizio, è stato generato un proxy WCF, è stata configurata un'applicazione client WCF, quindi è stato utilizzato il proxy per chiamare le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="03b5e-117">You defined a service contract, implemented the service contract, generated a WCF proxy, configured a WCF client application, and then used the proxy to call service operations.</span></span> <span data-ttu-id="03b5e-118">Per testare l'applicazione, eseguire innanzitutto GettingStartedHost per avviare il servizio e quindi eseguire GettingStartedClient.</span><span class="sxs-lookup"><span data-stu-id="03b5e-118">To test out the application, first run GettingStartedHost to start the service and then run GettingStartedClient.</span></span>

<span data-ttu-id="03b5e-119">L'aspetto dell'output da GettingStartedHost è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="03b5e-119">The output from GettingStartedHost should look like this:</span></span>

```text
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714
```

<span data-ttu-id="03b5e-120">L'aspetto dell'output da GettingStartedClient è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="03b5e-120">The output from GettingStartedClient should look like this:</span></span>

```text
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.
```

## <a name="see-also"></a><span data-ttu-id="03b5e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03b5e-121">See also</span></span>

- [<span data-ttu-id="03b5e-122">Creazione di client</span><span class="sxs-lookup"><span data-stu-id="03b5e-122">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)
- [<span data-ttu-id="03b5e-123">Procedura: Creare un client</span><span class="sxs-lookup"><span data-stu-id="03b5e-123">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="03b5e-124">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="03b5e-124">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)
- [<span data-ttu-id="03b5e-125">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="03b5e-125">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="03b5e-126">Procedura: Creare un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="03b5e-126">How to: Create a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="03b5e-127">Procedura: Accedere ai servizi con un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="03b5e-127">How to: Access Services with a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="03b5e-128">Introduzione</span><span class="sxs-lookup"><span data-stu-id="03b5e-128">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="03b5e-129">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="03b5e-129">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)