---
title: Hosting del servizio dati (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, Windows Communication Foundation
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
ms.openlocfilehash: 1464880e92753d2774b1ca60d55c71a88d8e9b15
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519388"
---
# <a name="hosting-the-data-service-wcf-data-services"></a><span data-ttu-id="20610-102">Hosting del servizio dati (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="20610-102">Hosting the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="20610-103">Tramite WCF Data Services, è possibile creare un servizio che espone dati come un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span><span class="sxs-lookup"><span data-stu-id="20610-103">By using WCF Data Services, you can create a service that exposes data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> <span data-ttu-id="20610-104">Questo servizio dati è definito come una classe che eredita da <xref:System.Data.Services.DataService%601>.</span><span class="sxs-lookup"><span data-stu-id="20610-104">This data service is defined as a class that inherits from <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="20610-105">Questa classe fornisce la funzionalità necessaria per elaborare i messaggi di richiesta, eseguire aggiornamenti sull'origine dati e generare messaggi di risposta, come richiesto da OData.</span><span class="sxs-lookup"><span data-stu-id="20610-105">This class provides the functionality required to process request messages, perform updates against the data source, and generate responses messages, as required by OData.</span></span> <span data-ttu-id="20610-106">Tuttavia, un servizio dati non è possibile associare a e restare in ascolto su un socket di rete per le richieste HTTP in ingresso.</span><span class="sxs-lookup"><span data-stu-id="20610-106">However, a data service cannot bind to and listen on a network socket for incoming HTTP requests.</span></span> <span data-ttu-id="20610-107">Per questa funzionalità obbligatoria, il servizio dati si basa su un componente di hosting.</span><span class="sxs-lookup"><span data-stu-id="20610-107">For this required functionality, the data service relies on a hosting component.</span></span>

 <span data-ttu-id="20610-108">L'host del servizio dati esegue le attività seguenti per conto del servizio dati:</span><span class="sxs-lookup"><span data-stu-id="20610-108">The data service host performs the following tasks on behalf of the data service:</span></span>

-   <span data-ttu-id="20610-109">È in attesa delle richieste e le indirizza al servizio dati.</span><span class="sxs-lookup"><span data-stu-id="20610-109">Listens for requests and routes these requests to the data service.</span></span>

-   <span data-ttu-id="20610-110">Crea un'istanza del servizio dati per ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="20610-110">Creates an instance of the data service for each request.</span></span>

-   <span data-ttu-id="20610-111">Richiede che il servizio dati elabori la richiesta in ingresso.</span><span class="sxs-lookup"><span data-stu-id="20610-111">Requests that the data service process the incoming request.</span></span>

-   <span data-ttu-id="20610-112">Invia la risposta per conto del servizio dati.</span><span class="sxs-lookup"><span data-stu-id="20610-112">Sends the response on behalf of the data service.</span></span>

 <span data-ttu-id="20610-113">Per semplificare l'hosting di un servizio dati, WCF Data Services è progettato per l'integrazione con Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="20610-113">To simplify hosting a data service, WCF Data Services is designed to integrate with Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="20610-114">Il servizio dati fornisce un'implementazione WCF predefinita che funge da host del servizio dati in un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="20610-114">The data service provides a default WCF implementation that serves as the data service host in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="20610-115">È pertanto possibile ospitare un servizio dati in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="20610-115">Therefore, you can host a data service in one of the following ways:</span></span>

-   <span data-ttu-id="20610-116">In un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20610-116">In an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span>

-   <span data-ttu-id="20610-117">In un'applicazione gestita che supporta servizi WCF indipendenti.</span><span class="sxs-lookup"><span data-stu-id="20610-117">In a managed application that supports self-hosted WCF services.</span></span>

-   <span data-ttu-id="20610-118">In un altro host del servizio dati personalizzato.</span><span class="sxs-lookup"><span data-stu-id="20610-118">In some other custom data service host.</span></span>

## <a name="hosting-a-data-service-in-an-aspnet-application"></a><span data-ttu-id="20610-119">Hosting di un servizio dati in un'applicazione ASP.NET</span><span class="sxs-lookup"><span data-stu-id="20610-119">Hosting a Data Service in an ASP.NET Application</span></span>

<span data-ttu-id="20610-120">Quando si usa la **Aggiungi nuovo elemento** finestra di dialogo in Visual Studio 2015, per definire un servizio dati in un'applicazione ASP.NET, lo strumento genera due nuovi file nel progetto.</span><span class="sxs-lookup"><span data-stu-id="20610-120">When you use the **Add New Item** dialog in Visual Studio 2015 to define a data service in an ASP.NET application, the tool generates two new files in the project.</span></span> <span data-ttu-id="20610-121">Il primo file presenta un'estensione `.svc` e indica al runtime WCF come creare un'istanza del servizio dati.</span><span class="sxs-lookup"><span data-stu-id="20610-121">The first file has a `.svc` extension and instructs the WCF runtime how to instantiate the data service.</span></span> <span data-ttu-id="20610-122">Di seguito è riportato un esempio di questo file per il servizio dati di esempio Northwind creato al completamento di [Guida introduttiva](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md):</span><span class="sxs-lookup"><span data-stu-id="20610-122">The following is an example of this file for the Northwind sample data service created when you complete the [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md):</span></span>

```
<%@ ServiceHost Language="C#"
    Factory="System.Data.Services.DataServiceHostFactory,
            System.Data.Services, Version=4.0.0.0,
            Culture=neutral, PublicKeyToken=b77a5c561934e089"
    Service="NorthwindService.Northwind" %>
```

 <span data-ttu-id="20610-123">Questa direttiva richiede all'applicazione la creazione dell'host del servizio per la classe di servizi dati denominata tramite la classe <xref:System.Data.Services.DataServiceHostFactory>.</span><span class="sxs-lookup"><span data-stu-id="20610-123">This directive tells the application to create the service host for the named data service class by using the <xref:System.Data.Services.DataServiceHostFactory> class.</span></span>

 <span data-ttu-id="20610-124">La pagina code-behind per il file `.svc` contiene la classe che corrisponde all'implementazione del servizio dati stesso, definita come segue per il servizio dati di esempio di Northwind:</span><span class="sxs-lookup"><span data-stu-id="20610-124">The code-behind page for the `.svc` file contains the class that is the implementation of the data service itself, which is defined as follows for the Northwind sample data service:</span></span>

 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]

 <span data-ttu-id="20610-125">Poiché un servizio dati si comporta come un servizio WCF, si integra con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] e segue il modello di programmazione Web di WCF.</span><span class="sxs-lookup"><span data-stu-id="20610-125">Because a data service behaves like a WCF service, the data service integrates with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] and follows the WCF Web programming model.</span></span> <span data-ttu-id="20610-126">Per altre informazioni, vedere [servizi WCF e ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) e [modello di programmazione HTTP Web WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).</span><span class="sxs-lookup"><span data-stu-id="20610-126">For more information, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) and [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).</span></span>

## <a name="self-hosted-wcf-services"></a><span data-ttu-id="20610-127">Servizi WCF indipendenti</span><span class="sxs-lookup"><span data-stu-id="20610-127">Self-Hosted WCF Services</span></span>
 <span data-ttu-id="20610-128">Poiché incorpora un'implementazione WCF, WCF Data Services supporta self-hosting di un servizio dati come un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="20610-128">Because it incorporates a WCF implementation, WCF Data Services support self-hosting a data service as a WCF service.</span></span> <span data-ttu-id="20610-129">Un servizio può essere indipendente in tutte le applicazioni [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], quale un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="20610-129">A service can be self-hosted in any [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application, such as a console application.</span></span> <span data-ttu-id="20610-130">La classe <xref:System.Data.Services.DataServiceHost>, che eredita da <xref:System.ServiceModel.Web.WebServiceHost>, viene usata per creare un'istanza del servizio dati in un indirizzo specifico.</span><span class="sxs-lookup"><span data-stu-id="20610-130">The <xref:System.Data.Services.DataServiceHost> class, which inherits from <xref:System.ServiceModel.Web.WebServiceHost>, is used to instantiate the data service at a specific address.</span></span>

 <span data-ttu-id="20610-131">Il self-hosting può essere usato per lo sviluppo e il test in quanto semplifica la distribuzione del servizio e la risoluzione dei relativi problemi.</span><span class="sxs-lookup"><span data-stu-id="20610-131">Self-hosting can be used for development and testing because it can make it easier to deploy and troubleshoot the service.</span></span> <span data-ttu-id="20610-132">Questo tipo di hosting non fornisce tuttavia le funzionalità avanzate di gestione e hosting offerte da [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] o da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="20610-132">However, this kind of hosting does not provide the advanced hosting and management features provided by [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] or by Internet Information Services (IIS).</span></span> <span data-ttu-id="20610-133">Per altre informazioni, vedere [Hosting in un'applicazione gestita](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="20610-133">For more information, see [Hosting in a Managed Application](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>

## <a name="defining-a-custom-data-service-host"></a><span data-ttu-id="20610-134">Definizione di un host del servizio dati personalizzato</span><span class="sxs-lookup"><span data-stu-id="20610-134">Defining a Custom Data Service Host</span></span>
 <span data-ttu-id="20610-135">Per i casi in cui l'implementazione dell'host WCF è troppo restrittiva, è anche possibile definire un host personalizzato per un servizio dati.</span><span class="sxs-lookup"><span data-stu-id="20610-135">For cases where the WCF host implementation is too restrictive, you can also define a custom host for a data service.</span></span> <span data-ttu-id="20610-136">Qualsiasi classe che implementi l'interfaccia <xref:System.Data.Services.IDataServiceHost> può essere usata come host di rete per un servizio dati.</span><span class="sxs-lookup"><span data-stu-id="20610-136">Any class that implements <xref:System.Data.Services.IDataServiceHost> interface can be used as the network host for a data service.</span></span> <span data-ttu-id="20610-137">Un host personalizzato deve implementare l'interfaccia <xref:System.Data.Services.IDataServiceHost> e deve essere in grado di gestire le responsabilità di base seguenti dell'host del servizio dati:</span><span class="sxs-lookup"><span data-stu-id="20610-137">A custom host must implement the <xref:System.Data.Services.IDataServiceHost> interface and be able to handle the following basic responsibilities of the data service host:</span></span>

-   <span data-ttu-id="20610-138">Fornire al servizio dati il percorso radice del servizio.</span><span class="sxs-lookup"><span data-stu-id="20610-138">Provide the data service with the service root path.</span></span>

-   <span data-ttu-id="20610-139">Elaborare le informazioni delle intestazioni di richieste e risposte per l'implementazione del membro <xref:System.Data.Services.IDataServiceHost> appropriato.</span><span class="sxs-lookup"><span data-stu-id="20610-139">Process request and response headers information to the appropriate <xref:System.Data.Services.IDataServiceHost> member implementation.</span></span>

-   <span data-ttu-id="20610-140">Gestire le eccezioni generate dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="20610-140">Handle exceptions raised by the data service.</span></span>

-   <span data-ttu-id="20610-141">Convalidare i parametri contenuti nella stringa di query.</span><span class="sxs-lookup"><span data-stu-id="20610-141">Validate parameters in the query string.</span></span>

## <a name="see-also"></a><span data-ttu-id="20610-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20610-142">See also</span></span>

- [<span data-ttu-id="20610-143">Definizione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="20610-143">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [<span data-ttu-id="20610-144">Esposizione dei dati come un servizio</span><span class="sxs-lookup"><span data-stu-id="20610-144">Exposing Your Data as a Service</span></span>](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
- [<span data-ttu-id="20610-145">Configurazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="20610-145">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
