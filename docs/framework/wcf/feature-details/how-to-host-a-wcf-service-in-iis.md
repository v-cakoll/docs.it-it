---
title: 'Procedura: ospitare un servizio WCF in IIS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: 326a270c4af38738c910828acd483070ab02ecd1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593087"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="172ff-102">Procedura: ospitare un servizio WCF in IIS</span><span class="sxs-lookup"><span data-stu-id="172ff-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="172ff-103">In questo argomento vengono illustrati i passaggi di base necessari per creare un servizio Windows Communication Foundation (WCF) ospitato in Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="172ff-103">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="172ff-104">Questo argomento presuppone la conoscenza di IIS e la comprensione dello strumento di gestione IIS per creare e gestire applicazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="172ff-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> <span data-ttu-id="172ff-105">Per ulteriori informazioni su IIS, vedere [Internet Information Services](https://www.iis.net/).</span><span class="sxs-lookup"><span data-stu-id="172ff-105">For more information about IIS see [Internet Information Services](https://www.iis.net/).</span></span> <span data-ttu-id="172ff-106">Un servizio WCF in esecuzione nell'ambiente IIS sfrutta appieno le funzionalità di IIS, ad esempio il riciclo dei processi, l'arresto inattivo, il monitoraggio dell'integrità dei processi e l'attivazione basata su messaggi.</span><span class="sxs-lookup"><span data-stu-id="172ff-106">A WCF service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="172ff-107">Questa opzione di hosting richiede che IIS sia configurato correttamente, ma non richiede la scrittura di codice di hosting come parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="172ff-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="172ff-108">È possibile utilizzare l'hosting IIS solo con un trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="172ff-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 <span data-ttu-id="172ff-109">Per ulteriori informazioni sull'interazione tra WCF e ASP.NET, vedere [servizi WCF e ASP.NET](wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="172ff-109">For more information about how WCF and ASP.NET interact, see [WCF Services and ASP.NET](wcf-services-and-aspnet.md).</span></span> <span data-ttu-id="172ff-110">Per ulteriori informazioni sulla configurazione della sicurezza, vedere [sicurezza](security.md).</span><span class="sxs-lookup"><span data-stu-id="172ff-110">For more information about configuring security, see [Security](security.md).</span></span>  
  
 <span data-ttu-id="172ff-111">Per la copia di origine di questo esempio, vedere la pagina relativa all' [hosting di IIS con il codice inline](../samples/iis-hosting-using-inline-code.md).</span><span class="sxs-lookup"><span data-stu-id="172ff-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="172ff-112">Per creare un servizio ospitato da IIS</span><span class="sxs-lookup"><span data-stu-id="172ff-112">To create a service hosted by IIS</span></span>  
  
1. <span data-ttu-id="172ff-113">Confermare che IIS sia installato e in esecuzione nel computer.</span><span class="sxs-lookup"><span data-stu-id="172ff-113">Confirm that IIS is installed and running on your computer.</span></span> <span data-ttu-id="172ff-114">Per ulteriori informazioni sull'installazione e la configurazione di IIS, vedere [installazione e configurazione di iis 7,0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista)</span><span class="sxs-lookup"><span data-stu-id="172ff-114">For more information about installing and configuring IIS see [Installing and Configuring IIS 7.0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista)</span></span>  
  
2. <span data-ttu-id="172ff-115">Creare una nuova cartella per i file dell'applicazione denominata "IISHostedCalcService", assicurarsi che ASP.NET abbia accesso al contenuto della cartella e utilizzare lo strumento di gestione IIS per creare una nuova applicazione IIS che si trova fisicamente in questa directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="172ff-115">Create a new folder for your application files called "IISHostedCalcService", ensure that ASP.NET has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="172ff-116">Quando si crea un alias per la directory dell'applicazione utilizzare "IISHostedCalc".</span><span class="sxs-lookup"><span data-stu-id="172ff-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3. <span data-ttu-id="172ff-117">Creare un nuovo file "service.svc" nella directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="172ff-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="172ff-118">Modificare questo file aggiungendo l'elemento seguente @ServiceHost .</span><span class="sxs-lookup"><span data-stu-id="172ff-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
   ```
   <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>
   ```  
  
4. <span data-ttu-id="172ff-119">Creare una sottodirectory App_Code all'interno della directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="172ff-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5. <span data-ttu-id="172ff-120">Creare un file di codice denominato Service.cs nella sottodirectory App_Code.</span><span class="sxs-lookup"><span data-stu-id="172ff-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6. <span data-ttu-id="172ff-121">Aggiungere le istruzioni using riportate di seguito all'inizio del file Service.cs.</span><span class="sxs-lookup"><span data-stu-id="172ff-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7. <span data-ttu-id="172ff-122">Aggiungere la seguente dichiarazione dello spazio dei nomi dopo le istruzioni using.</span><span class="sxs-lookup"><span data-stu-id="172ff-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8. <span data-ttu-id="172ff-123">Definire il contratto di servizio all'interno della dichiarazione dello spazio dei nomi come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="172ff-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="172ff-124">Implementare il contratto di servizio dopo la sua definizione come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="172ff-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="172ff-125">Creare un file denominato "Web.config" e aggiungere il codice di configurazione seguente nel file.</span><span class="sxs-lookup"><span data-stu-id="172ff-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="172ff-126">In fase di esecuzione, l'infrastruttura WCF utilizza le informazioni per costruire un endpoint con cui le applicazioni client possono comunicare.</span><span class="sxs-lookup"><span data-stu-id="172ff-126">At runtime, the WCF infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]
  
     <span data-ttu-id="172ff-127">In questo esempio vengono specificati in modo esplicito gli endpoint del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="172ff-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="172ff-128">Se non vengono aggiunti endpoint al servizio, il runtime aggiunge gli endpoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="172ff-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="172ff-129">Per ulteriori informazioni sugli endpoint, le associazioni e i comportamenti predefiniti, vedere [Configurazione semplificata](../simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="172ff-129">For more information about default endpoints, bindings, and behaviors see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="172ff-130">Per assicurarsi che il servizio sia ospitato correttamente, aprire un'istanza di Internet Explorer e passare all'URL del servizio: `http://localhost/IISHostedCalc/Service.svc`</span><span class="sxs-lookup"><span data-stu-id="172ff-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="172ff-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="172ff-131">Example</span></span>  
 <span data-ttu-id="172ff-132">Di seguito è riportato un elenco completo del codice per il servizio calcolatrice ospitato da IIS.</span><span class="sxs-lookup"><span data-stu-id="172ff-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)]
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)]
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="172ff-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="172ff-133">See also</span></span>

- [<span data-ttu-id="172ff-134">Host in Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="172ff-134">Hosting in Internet Information Services</span></span>](hosting-in-internet-information-services.md)
- [<span data-ttu-id="172ff-135">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="172ff-135">Hosting Services</span></span>](../hosting-services.md)
- [<span data-ttu-id="172ff-136">Servizi WCF e ASP.NET</span><span class="sxs-lookup"><span data-stu-id="172ff-136">WCF Services and ASP.NET</span></span>](wcf-services-and-aspnet.md)
- [<span data-ttu-id="172ff-137">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="172ff-137">Security</span></span>](security.md)
- <span data-ttu-id="172ff-138">[Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="172ff-138">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
