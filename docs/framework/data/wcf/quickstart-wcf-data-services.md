---
title: Guida rapida (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f945d33a4fc789b3c73c1c80040fc8527301758b
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121217"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="eb1a2-102">Guida rapida (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="eb1a2-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="eb1a2-103">Questa guida introduttiva consente di acquisire familiarità con WCF Data ServicesWCF Data Services e il protocollo OData (Open Data Protocol) tramite una serie di attività che supportano gli argomenti in [Guida introduttiva](getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="eb1a2-103">This quickstart helps you become familiar with WCF Data Services and the Open Data Protocol (OData) through a series of tasks that support the topics in [Getting Started](getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="eb1a2-104">Contenuto dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="eb1a2-104">What you'll learn</span></span>

<span data-ttu-id="eb1a2-105">Nella prima attività di questa guida introduttiva viene illustrato come creare un servizio dati per esporre un feed OData dal database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="eb1a2-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="eb1a2-106">Negli argomenti successivi si accederà al feed OData utilizzando un browser Web e si creerà anche un'applicazione client Windows Presentation Foundation (WPF) che utilizza il feed OData utilizzando le librerie client.</span><span class="sxs-lookup"><span data-stu-id="eb1a2-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eb1a2-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="eb1a2-107">Prerequisites</span></span>

<span data-ttu-id="eb1a2-108">Per completare questa guida introduttiva, installare i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb1a2-108">To complete this quickstart, install the following components:</span></span>

- <span data-ttu-id="eb1a2-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="eb1a2-109">Visual Studio</span></span>

- <span data-ttu-id="eb1a2-110">Istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eb1a2-110">An instance of SQL Server.</span></span> <span data-ttu-id="eb1a2-111">Ciò include SQL Server Express, incluso in un'installazione predefinita di Visual Studio 2015 o come parte del carico di lavoro di **archiviazione ed elaborazione** dei dati in Visual Studio 2017 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="eb1a2-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017 or later.</span></span>

- <span data-ttu-id="eb1a2-112">Il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="eb1a2-112">The Northwind sample database.</span></span> <span data-ttu-id="eb1a2-113">Per installare il database, eseguire lo script Transact-SQL da [Northwind e pubs database di esempio per Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span><span class="sxs-lookup"><span data-stu-id="eb1a2-113">To install the database, run the Transact-SQL script from [Northwind and pubs sample databases for Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="eb1a2-114">Attività introduttive dei servizi dati WCFWCF data services quickstart tasks</span><span class="sxs-lookup"><span data-stu-id="eb1a2-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="eb1a2-115">Creare il servizio datiCreate the Data Service</span><span class="sxs-lookup"><span data-stu-id="eb1a2-115">Create the Data Service</span></span>](creating-the-data-service.md)

 <span data-ttu-id="eb1a2-116">Definire l'applicazione ASP.NET, definire il modello di dati, creare il servizio dati e abilitare l'accesso alle risorse.</span><span class="sxs-lookup"><span data-stu-id="eb1a2-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="eb1a2-117">Accedere al servizio da un browser Web</span><span class="sxs-lookup"><span data-stu-id="eb1a2-117">Access the Service from a Web Browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="eb1a2-118">Avviare il servizio da Visual Studio e accedervi inviando richieste GET HTTP attraverso un browser al feed esposto.</span><span class="sxs-lookup"><span data-stu-id="eb1a2-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="eb1a2-119">Creare l'applicazione client .NET FrameworkCreate the .NET Framework Client Application</span><span class="sxs-lookup"><span data-stu-id="eb1a2-119">Create the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="eb1a2-120">Creare un'app WPF per usare il feed OData, associare dati ai controlli Windows, modificare i dati nei controlli associati e quindi inviare le modifiche al servizio dati.</span><span class="sxs-lookup"><span data-stu-id="eb1a2-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="eb1a2-121">I file di progetto da una versione completata della guida introduttiva possono essere scaricati da [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).</span><span class="sxs-lookup"><span data-stu-id="eb1a2-121">Project files from a completed version of the quickstart can be downloaded from [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).</span></span>

## <a name="next-steps"></a><span data-ttu-id="eb1a2-122">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="eb1a2-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="eb1a2-123">Avviare la guida introduttiva</span><span class="sxs-lookup"><span data-stu-id="eb1a2-123">Start the quickstart</span></span>](creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="eb1a2-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb1a2-124">See also</span></span>

- [<span data-ttu-id="eb1a2-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="eb1a2-125">ADO.NET Entity Framework</span></span>](../adonet/ef/index.md)
