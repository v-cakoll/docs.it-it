---
title: Guida rapida (WCF Data Services)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa6711ef5591110c74a1da95358aac4d8a8da655
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="a54fe-102">Guida rapida (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="a54fe-102">Quickstart (WCF Data Services)</span></span>
<span data-ttu-id="a54fe-103">Questa Guida introduttiva per acquisire familiarità con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] e [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] attraverso una serie di attività che supportano gli argomenti di [Introduzione](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a54fe-103">This quickstart helps you become familiar with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="a54fe-104">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="a54fe-104">What You Will Learn</span></span>  
 <span data-ttu-id="a54fe-105">La prima attività di questa guida rapida prevede la creazione di un servizio dati per l'esposizione di un feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] dal database Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="a54fe-105">The first task in this quickstart shows how to create a data service to expose an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed from the Northwind sample database.</span></span> <span data-ttu-id="a54fe-106">Negli argomenti successivi si procederà all'accesso al feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] usando un browser e verrà creata un'applicazione client di [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] che usa il feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] tramite librerie client.</span><span class="sxs-lookup"><span data-stu-id="a54fe-106">In later topics, you will access the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by using a Web browser, and also create a [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] client application that consumes the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by using client libraries.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a54fe-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a54fe-107">Prerequisites</span></span>  
 <span data-ttu-id="a54fe-108">Per completare le attività incluse nella guida rapida, è necessario installare i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a54fe-108">To complete this quickstart, you must install the following components:</span></span>  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]<span data-ttu-id="a54fe-109">.</span><span class="sxs-lookup"><span data-stu-id="a54fe-109">.</span></span>  
  
-   <span data-ttu-id="a54fe-110">Un'istanza di [!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a54fe-110">An instance of [!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a54fe-111">con SQL Server Express, che fa parte dell'installazione predefinita di [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a54fe-111">This includes SQL Server Express, which is included in a default installation of [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
-   <span data-ttu-id="a54fe-112">Il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="a54fe-112">The Northwind sample database.</span></span> <span data-ttu-id="a54fe-113">Per scaricare questo database di esempio, vedere la pagina di download dei [database di esempio per SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span><span class="sxs-lookup"><span data-stu-id="a54fe-113">To download this sample database, see the download page, [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span></span>  
  
## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="a54fe-114">Attività della guida rapida di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="a54fe-114">WCF Data Services Quickstart Tasks</span></span>  
 [<span data-ttu-id="a54fe-115">Creazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="a54fe-115">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
 <span data-ttu-id="a54fe-116">Definire l'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , definire il modello di dati, creare il servizio dati e abilitare l'accesso alle risorse.</span><span class="sxs-lookup"><span data-stu-id="a54fe-116">Define the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application, define the data model, create the data service, and enable access to resources.</span></span>  
  
 [<span data-ttu-id="a54fe-117">Accesso al servizio da un Web browser</span><span class="sxs-lookup"><span data-stu-id="a54fe-117">Accessing the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
 <span data-ttu-id="a54fe-118">Avviare il servizio da [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] e accedervi inviando richieste GET HTTP attraverso un browser al feed esposto.</span><span class="sxs-lookup"><span data-stu-id="a54fe-118">Start the service from [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>  
  
 [<span data-ttu-id="a54fe-119">Creazione dell'applicazione client .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a54fe-119">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
 <span data-ttu-id="a54fe-120">Creare un'applicazione client [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] per usare il feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] , associare dati a controlli Windows, modificare dati nei controlli associati e restituire quindi le modifiche al servizio dati.</span><span class="sxs-lookup"><span data-stu-id="a54fe-120">Create a [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] client application to consume the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a54fe-121">I file di progetto di una versione completa della guida rapida possono essere scaricati dalla pagina degli [esempi di documentazione di WCF Data Services](http://go.microsoft.com/fwlink/?LinkId=179994) .</span><span class="sxs-lookup"><span data-stu-id="a54fe-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](http://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a54fe-122">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a54fe-122">Next Steps</span></span>  
 <span data-ttu-id="a54fe-123">[Avviare la guida rapida](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="a54fe-123">[Start the Quickstart](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a54fe-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a54fe-124">See Also</span></span>  
 [<span data-ttu-id="a54fe-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="a54fe-125">ADO.NET Entity Framework</span></span>](../../../../docs/framework/data/adonet/ef/index.md)
