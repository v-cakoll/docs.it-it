---
title: Guida rapida (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: 49d11556d3703331b4cdf5bf83a69f6b15bca8ed
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881987"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="8108c-102">Guida rapida (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="8108c-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="8108c-103">Questa Guida introduttiva consente di acquisire familiarità con WCF Data Services e il [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] attraverso una serie di attività che supportano gli argomenti in [introduttiva](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8108c-103">This quickstart helps you become familiar with WCF Data Services and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="8108c-104">Contenuto dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="8108c-104">What you'll learn</span></span>

<span data-ttu-id="8108c-105">La prima attività in questa Guida introduttiva illustra come creare un servizio dati per esporre un feed OData da database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="8108c-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="8108c-106">Negli argomenti successivi si accederà OData feed usando un Web browser, nonché creare un Windows Presentation Foundation (WPF) applicazione client che utilizza OData feed usando le librerie client.</span><span class="sxs-lookup"><span data-stu-id="8108c-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8108c-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8108c-107">Prerequisites</span></span>

<span data-ttu-id="8108c-108">Per completare le attività incluse nella guida rapida, è necessario installare i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8108c-108">To complete this quickstart, you must install the following components:</span></span>

- <span data-ttu-id="8108c-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8108c-109">Visual Studio</span></span>

- <span data-ttu-id="8108c-110">Un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8108c-110">An instance of SQL Server.</span></span> <span data-ttu-id="8108c-111">Ciò include SQL Server Express, incluso in un'installazione predefinita di Visual Studio 2015 o come parte del **elaborazione ed archiviazione dati** carico di lavoro in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="8108c-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017.</span></span>

- <span data-ttu-id="8108c-112">Il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="8108c-112">The Northwind sample database.</span></span> <span data-ttu-id="8108c-113">Per scaricare questo database di esempio, vedere la pagina di download dei [database di esempio per SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span><span class="sxs-lookup"><span data-stu-id="8108c-113">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="8108c-114">Attività della Guida rapida di WCF data services</span><span class="sxs-lookup"><span data-stu-id="8108c-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="8108c-115">Creare il servizio dati</span><span class="sxs-lookup"><span data-stu-id="8108c-115">Create the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

 <span data-ttu-id="8108c-116">Definire l'applicazione ASP.NET, definire il modello di dati, creare il servizio dati e abilitare l'accesso alle risorse.</span><span class="sxs-lookup"><span data-stu-id="8108c-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="8108c-117">Accedere al servizio da un Web Browser</span><span class="sxs-lookup"><span data-stu-id="8108c-117">Access the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="8108c-118">Avviare il servizio da Visual Studio e accedervi inviando richieste GET HTTP attraverso un browser al feed esposto.</span><span class="sxs-lookup"><span data-stu-id="8108c-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="8108c-119">Creare l'applicazione Client di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8108c-119">Create the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="8108c-120">Creare un'app WPF per usare il feed OData, associare dati a controlli Windows, modificare i dati nei controlli associati e restituire quindi le modifiche al servizio dati.</span><span class="sxs-lookup"><span data-stu-id="8108c-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="8108c-121">I file di progetto di una versione completa della guida rapida possono essere scaricati dalla pagina degli [esempi di documentazione di WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=179994) .</span><span class="sxs-lookup"><span data-stu-id="8108c-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8108c-122">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8108c-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8108c-123">Avviare la Guida rapida</span><span class="sxs-lookup"><span data-stu-id="8108c-123">Start the quickstart</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="8108c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8108c-124">See also</span></span>

- [<span data-ttu-id="8108c-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="8108c-125">ADO.NET Entity Framework</span></span>](../../../../docs/framework/data/adonet/ef/index.md)
