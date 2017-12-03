---
title: 'Procedura: ospitare un servizio WCF in IIS'
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
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 934b5d16cdea7026e0e7874cf04ab53c8fbdf58e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="9f299-102">Procedura: ospitare un servizio WCF in IIS</span><span class="sxs-lookup"><span data-stu-id="9f299-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="9f299-103">In questo argomento vengono delineati i passaggi di base necessari per creare un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ospitato in Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="9f299-103">This topic outlines the basic steps required to create a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="9f299-104">Questo argomento presuppone la conoscenza di IIS e la comprensione dello strumento di gestione IIS per creare e gestire applicazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="9f299-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9f299-105">IIS vedere [Internet Information Services](http://go.microsoft.com/fwlink/?LinkId=132449).</span><span class="sxs-lookup"><span data-stu-id="9f299-105"> IIS see [Internet Information Services](http://go.microsoft.com/fwlink/?LinkId=132449).</span></span> <span data-ttu-id="9f299-106">Un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in esecuzione nell'ambiente IIS sfrutta appieno le funzionalità IIS, quali il riciclo dei processi, la chiusura per inattività, il monitoraggio dell'integrità dei processi e l'attivazione basata su messaggi.</span><span class="sxs-lookup"><span data-stu-id="9f299-106">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="9f299-107">Questa opzione di hosting richiede che IIS sia configurato correttamente, ma non richiede la scrittura di codice di hosting come parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9f299-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="9f299-108">È possibile utilizzare l'hosting IIS solo con un trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="9f299-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9f299-109">come [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interagire, vedere [servizi WCF e ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="9f299-109"> how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interact, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9f299-110">configurazione della protezione, vedere [sicurezza](../../../../docs/framework/wcf/feature-details/security.md).</span><span class="sxs-lookup"><span data-stu-id="9f299-110"> configuring security, see [Security](../../../../docs/framework/wcf/feature-details/security.md).</span></span>  
  
 <span data-ttu-id="9f299-111">Per la copia di origine di questo esempio, vedere [IIS che ospita utilizzando il codice Inline](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span><span class="sxs-lookup"><span data-stu-id="9f299-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="9f299-112">Per creare un servizio ospitato da IIS</span><span class="sxs-lookup"><span data-stu-id="9f299-112">To create a service hosted by IIS</span></span>  
  
1.  <span data-ttu-id="9f299-113">Confermare che IIS sia installato e in esecuzione nel computer.</span><span class="sxs-lookup"><span data-stu-id="9f299-113">Confirm that IIS is installed and running on your computer.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9f299-114">l'installazione e configurazione di IIS vedere [installazione e configurazione di IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=132128)</span><span class="sxs-lookup"><span data-stu-id="9f299-114"> installing and configuring IIS see [Installing and Configuring IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=132128)</span></span>  
  
2.  <span data-ttu-id="9f299-115">Creare una nuova cartella per i file dell'applicazione denominata "IISHostedCalcService", assicurarsi che [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] abbia accesso al contenuto della cartella e utilizzare lo strumento di gestione IIS per creare una nuova applicazione IIS situata fisicamente in questa directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9f299-115">Create a new folder for your application files called "IISHostedCalcService", ensure that [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="9f299-116">Quando si crea un alias per la directory dell'applicazione utilizzare "IISHostedCalc".</span><span class="sxs-lookup"><span data-stu-id="9f299-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3.  <span data-ttu-id="9f299-117">Creare un nuovo file "service.svc" nella directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9f299-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="9f299-118">Modificare il file, aggiungere il codice seguente @ServiceHost elemento.</span><span class="sxs-lookup"><span data-stu-id="9f299-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>  
    ```  
  
4.  <span data-ttu-id="9f299-119">Creare una sottodirectory App_Code all'interno della directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9f299-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5.  <span data-ttu-id="9f299-120">Creare un file di codice denominato Service.cs nella sottodirectory App_Code.</span><span class="sxs-lookup"><span data-stu-id="9f299-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6.  <span data-ttu-id="9f299-121">Aggiungere le istruzioni using riportate di seguito all'inizio del file Service.cs.</span><span class="sxs-lookup"><span data-stu-id="9f299-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7.  <span data-ttu-id="9f299-122">Aggiungere la seguente dichiarazione dello spazio dei nomi dopo le istruzioni using.</span><span class="sxs-lookup"><span data-stu-id="9f299-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8.  <span data-ttu-id="9f299-123">Definire il contratto di servizio all'interno della dichiarazione dello spazio dei nomi come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9f299-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="9f299-124">Implementare il contratto di servizio dopo la sua definizione come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9f299-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="9f299-125">Creare un file denominato "Web.config" e aggiungere il codice di configurazione seguente nel file.</span><span class="sxs-lookup"><span data-stu-id="9f299-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="9f299-126">In fase di esecuzione, l'infrastruttura [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza le informazioni per costruire un endpoint con cui possano comunicare le applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="9f299-126">At runtime, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]      
  
     <span data-ttu-id="9f299-127">In questo esempio vengono specificati in modo esplicito gli endpoint del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9f299-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="9f299-128">Se non vengono aggiunti endpoint al servizio, il runtime aggiunge gli endpoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9f299-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9f299-129">predefinito endpoint, associazioni e comportamenti, vedere [configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9f299-129"> default endpoints, bindings, and behaviors see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="9f299-130">Per assicurarsi che il servizio sia ospitato correttamente, aprire un'istanza di Internet Explorer e passare all'URL del servizio: `http://localhost/IISHostedCalc/Service.svc`</span><span class="sxs-lookup"><span data-stu-id="9f299-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f299-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f299-131">Example</span></span>  
 <span data-ttu-id="9f299-132">Di seguito è riportato un elenco completo del codice per il servizio calcolatrice ospitato da IIS.</span><span class="sxs-lookup"><span data-stu-id="9f299-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)] 
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)] 
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="9f299-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f299-133">See Also</span></span>  
 [<span data-ttu-id="9f299-134">Hosting in Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="9f299-134">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [<span data-ttu-id="9f299-135">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="9f299-135">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="9f299-136">Servizi WCF e ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9f299-136">WCF Services and ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [<span data-ttu-id="9f299-137">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9f299-137">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
 [<span data-ttu-id="9f299-138">Windows Server AppFabric con funzionalità di Hosting</span><span class="sxs-lookup"><span data-stu-id="9f299-138">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
