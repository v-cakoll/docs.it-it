---
title: 'Procedura: creare un servizio HTTP Web WCF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 877662d3-d372-4e08-b417-51f66a0095cd
ms.openlocfilehash: 1b76d21cb4f416aae76e7597ad16cfd45e5b7cad
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47090555"
---
# <a name="how-to-create-a-basic-wcf-web-http-service"></a><span data-ttu-id="66556-102">Procedura: creare un servizio HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="66556-102">How to: Create a Basic WCF Web HTTP Service</span></span>

<span data-ttu-id="66556-103">Windows Communication Foundation (WCF) consente di creare un servizio che espone un endpoint Web.</span><span class="sxs-lookup"><span data-stu-id="66556-103">Windows Communication Foundation (WCF) allows you to create a service that exposes a Web endpoint.</span></span> <span data-ttu-id="66556-104">Gli endpoint Web inviano dati in XML o JSON, senza SOAP envelope.</span><span class="sxs-lookup"><span data-stu-id="66556-104">Web endpoints send data by XML or JSON, there is no SOAP envelope.</span></span> <span data-ttu-id="66556-105">In questo argomento viene dimostrato come esporre un endpoint di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="66556-105">This topic demonstrates how to expose such an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="66556-106">L'unico modo per proteggere un endpoint Web è esporlo tramite HTTPS utilizzando la sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="66556-106">The only way to secure a Web endpoint is to expose it through HTTPS, using transport security.</span></span> <span data-ttu-id="66556-107">Quando si utilizza la sicurezza basata sul messaggio, le informazioni sulla sicurezza vengono inserite generalmente nelle intestazioni SOAP e poiché i messaggi inviati a endpoint non SOAP non contengono SOAP envelope, non esiste altra posizione in cui inserire le informazioni sulla sicurezza ed è necessario affidarsi alla sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="66556-107">When using message-based security, security information is usually placed in SOAP headers and because the messages sent to non-SOAP endpoints contain no SOAP envelope, there is nowhere to place the security information and you must rely on transport security.</span></span>

## <a name="to-create-a-web-endpoint"></a><span data-ttu-id="66556-108">Per creare un endpoint Web</span><span class="sxs-lookup"><span data-stu-id="66556-108">To create a Web endpoint</span></span>

1. <span data-ttu-id="66556-109">Definire un contratto di servizio utilizzando un'interfaccia contrassegnata con gli attributi <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> e <xref:System.ServiceModel.Web.WebGetAttribute>.</span><span class="sxs-lookup"><span data-stu-id="66556-109">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes.</span></span>

     [!code-csharp[htBasicService#0](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#0)]
     [!code-vb[htBasicService#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#0)]

    > [!NOTE]
    > <span data-ttu-id="66556-110">Per impostazione predefinita, <xref:System.ServiceModel.Web.WebInvokeAttribute> esegue il mapping delle chiamate POST all'operazione.</span><span class="sxs-lookup"><span data-stu-id="66556-110">By default, <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="66556-111">È possibile tuttavia definire il metodo HTTP, ad esempio HEAD, PUT o DELETE, per eseguire il mapping all'operazione specificando un parametro "method=".</span><span class="sxs-lookup"><span data-stu-id="66556-111">You can, however, specify the HTTP method (for example, HEAD, PUT, or DELETE) to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="66556-112"><xref:System.ServiceModel.Web.WebGetAttribute> non dispone di un parametro "method=" ed esegue solo il mapping delle chiamate GET all'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="66556-112"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>

2. <span data-ttu-id="66556-113">Implementare il contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="66556-113">Implement the service contract.</span></span>

     [!code-csharp[htBasicService#1](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#1)]
     [!code-vb[htBasicService#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#1)]

## <a name="to-host-the-service"></a><span data-ttu-id="66556-114">Per ospitare il servizio</span><span class="sxs-lookup"><span data-stu-id="66556-114">To host the service</span></span>

1. <span data-ttu-id="66556-115">Creare un oggetto <xref:System.ServiceModel.Web.WebServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="66556-115">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span>

     [!code-csharp[htBasicService#2](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#2)]
     [!code-vb[htBasicService#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#2)]

2. <span data-ttu-id="66556-116">Aggiungere un <xref:System.ServiceModel.Description.ServiceEndpoint> con <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="66556-116">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>

     [!code-csharp[htBasicService#3](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#3)]
     [!code-vb[htBasicService#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#3)]

    > [!NOTE]
    > <span data-ttu-id="66556-117">Se non viene aggiunto un endpoint, l'oggetto <xref:System.ServiceModel.Web.WebServiceHost> ne crea automaticamente uno predefinito.</span><span class="sxs-lookup"><span data-stu-id="66556-117">If you do not add an endpoint, <xref:System.ServiceModel.Web.WebServiceHost> automatically creates a default endpoint.</span></span> <span data-ttu-id="66556-118"><xref:System.ServiceModel.Web.WebServiceHost> aggiunge anche <xref:System.ServiceModel.Description.WebHttpBehavior> e disabilita la pagina della Guida HTTP e la funzionalità GET WSDL (Web Services Description Language) in modo che l'endpoint dei metadati non interferisca con l'endpoint HTTP predefinito.</span><span class="sxs-lookup"><span data-stu-id="66556-118"><xref:System.ServiceModel.Web.WebServiceHost> also adds <xref:System.ServiceModel.Description.WebHttpBehavior> and disables the HTTP Help page and the Web Services Description Language (WSDL) GET functionality so the metadata endpoint does not interfere with the default HTTP endpoint.</span></span>
    >
    >  <span data-ttu-id="66556-119">L'aggiunta di un endpoint non SOAP con un URL "" provoca un comportamento imprevisto quando si tenta di chiamare un'operazione sull'endpoint.</span><span class="sxs-lookup"><span data-stu-id="66556-119">Adding a non-SOAP endpoint with a URL of "" causes unexpected behavior when an attempt is made to call an operation on the endpoint.</span></span> <span data-ttu-id="66556-120">Il motivo è l'URI dell'endpoint è identico a come URI per la pagina della Guida (la pagina visualizzata quando si passa all'indirizzo di base di un servizio WCF) di ascolto.</span><span class="sxs-lookup"><span data-stu-id="66556-120">The reason for this is the listen URI of the endpoint is the same as the URI for the help page (the page that is displayed when you browse to the base address of a WCF service).</span></span>

     <span data-ttu-id="66556-121">Per evitare che ciò accada è possibile svolgere una delle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="66556-121">You can do one of the following actions to prevent this from happening:</span></span>

    - <span data-ttu-id="66556-122">Specificare sempre un URI non vuoto per un endpoint non SOAP.</span><span class="sxs-lookup"><span data-stu-id="66556-122">Always specify a non-blank URI for a non-SOAP endpoint.</span></span>

    - <span data-ttu-id="66556-123">Disattivare la pagina della Guida.</span><span class="sxs-lookup"><span data-stu-id="66556-123">Turn off the help page.</span></span> <span data-ttu-id="66556-124">Questa operazione può essere eseguita con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="66556-124">This can be done with the following code:</span></span>

     [!code-csharp[htBasicService#4](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/snippets.cs#4)]
     [!code-vb[htBasicService#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/snippets.vb#4)]

3. <span data-ttu-id="66556-125">Aprire l'host del servizio e attendere finché l'utente non preme INVIO.</span><span class="sxs-lookup"><span data-stu-id="66556-125">Open the service host and wait until the user presses ENTER.</span></span>

     [!code-csharp[htBasicService#5](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/snippets.cs#5)]
     [!code-vb[htBasicService#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/snippets.vb#5)]

     <span data-ttu-id="66556-126">In questo esempio viene dimostrato come ospitare un servizio Web con un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="66556-126">This sample demonstrates how to host a Web-Style service with a console application.</span></span> <span data-ttu-id="66556-127">È anche possibile ospitare tale servizio all'interno di IIS.</span><span class="sxs-lookup"><span data-stu-id="66556-127">You can also host such a service within IIS.</span></span> <span data-ttu-id="66556-128">A questo scopo, specificare la classe <xref:System.ServiceModel.Activation.WebServiceHostFactory> in un file con estensione svc come è dimostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="66556-128">To do this, specify the <xref:System.ServiceModel.Activation.WebServiceHostFactory> class in a .svc file as the following code demonstrates.</span></span>

    ```
    <%ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Samples.Service"
        Factory=System.ServiceModel.Activation.WebServiceHostFactory%>
    ```

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="66556-129">Per chiamare operazioni del servizio mappate a GET in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="66556-129">To call service operations mapped to GET in Internet Explorer</span></span>

1. <span data-ttu-id="66556-130">Aprire Internet Explorer, digitare "`http://localhost:8000/EchoWithGet?s=Hello, world!`" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="66556-130">Open Internet Explorer and type "`http://localhost:8000/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="66556-131">L'URL contiene l'indirizzo di base del servizio (`http://localhost:8000/`), l'indirizzo relativo dell'endpoint (""), l'operazione del servizio da chiamare ("EchoWithGet") e un punto interrogativo seguito da un elenco di parametri denominati separati da una e commerciale (&).</span><span class="sxs-lookup"><span data-stu-id="66556-131">The URL contains the base address of the service (`http://localhost:8000/`), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>

## <a name="to-call-service-operations-in-code"></a><span data-ttu-id="66556-132">Per chiamare operazioni del servizio nel codice</span><span class="sxs-lookup"><span data-stu-id="66556-132">To call service operations in code</span></span>

1. <span data-ttu-id="66556-133">Creare un'istanza di <xref:System.ServiceModel.ChannelFactory%601> all'interno di un blocco `using`.</span><span class="sxs-lookup"><span data-stu-id="66556-133">Create an instance of <xref:System.ServiceModel.ChannelFactory%601> within a `using` block.</span></span>

     [!code-csharp[htBasicService#6](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#6)]
     [!code-vb[htBasicService#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#6)]

2. <span data-ttu-id="66556-134">Aggiungere <xref:System.ServiceModel.Description.WebHttpBehavior> all'endpoint che viene chiamato da <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="66556-134">Add <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint the <xref:System.ServiceModel.ChannelFactory%601> calls.</span></span>

     [!code-csharp[htBasicService#7](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#7)]
     [!code-vb[htBasicService#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#7)]

3. <span data-ttu-id="66556-135">Creare il canale e chiamare il servizio.</span><span class="sxs-lookup"><span data-stu-id="66556-135">Create the channel and call the service.</span></span>

     [!code-csharp[htBasicService#8](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#8)]
     [!code-vb[htBasicService#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#8)]

4. <span data-ttu-id="66556-136">Chiudere la classe <xref:System.ServiceModel.Web.WebServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="66556-136">Close the <xref:System.ServiceModel.Web.WebServiceHost>.</span></span>

     [!code-csharp[htBasicService#9](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#9)]
     [!code-vb[htBasicService#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#9)]

## <a name="example"></a><span data-ttu-id="66556-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="66556-137">Example</span></span>

<span data-ttu-id="66556-138">Di seguito è riportato il codice completo per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="66556-138">The following is the full code listing for this example.</span></span>

[!code-csharp[htBasicService#10](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#10)]
[!code-vb[htBasicService#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#10)]

## <a name="compiling-the-code"></a><span data-ttu-id="66556-139">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="66556-139">Compiling the code</span></span>

<span data-ttu-id="66556-140">Durante la compilazione di Service.cs fare riferimento a System.ServiceModel.dll e System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="66556-140">When compiling Service.cs reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>

## <a name="see-also"></a><span data-ttu-id="66556-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66556-141">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="66556-142">Modello di programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="66556-142">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)