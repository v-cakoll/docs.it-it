---
title: Guida rapida (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: df3151dfd3628231d84d2d128c61d1c0b6b0d48e
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74800359"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="027bb-102">Guida rapida (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="027bb-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="027bb-103">Questa Guida introduttiva consente di acquisire familiarità con WCF Data Services e il Open Data Protocol (OData) tramite una serie di attività che supportano gli argomenti in [Introduzione](getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="027bb-103">This quickstart helps you become familiar with WCF Data Services and the Open Data Protocol (OData) through a series of tasks that support the topics in [Getting Started](getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="027bb-104">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="027bb-104">What you'll learn</span></span>

<span data-ttu-id="027bb-105">Nella prima attività di questa Guida introduttiva viene illustrato come creare un servizio dati per esporre un feed OData dal database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="027bb-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="027bb-106">Negli argomenti successivi, sarà possibile accedere al feed OData utilizzando un Web browser e creare anche un'applicazione client Windows Presentation Foundation (WPF) che utilizza il feed OData utilizzando le librerie client.</span><span class="sxs-lookup"><span data-stu-id="027bb-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="027bb-107">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="027bb-107">Prerequisites</span></span>

<span data-ttu-id="027bb-108">Per completare le attività incluse nella guida rapida, è necessario installare i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="027bb-108">To complete this quickstart, you must install the following components:</span></span>

- <span data-ttu-id="027bb-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="027bb-109">Visual Studio</span></span>

- <span data-ttu-id="027bb-110">Istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="027bb-110">An instance of SQL Server.</span></span> <span data-ttu-id="027bb-111">Sono inclusi SQL Server Express, incluso in un'installazione predefinita di Visual Studio 2015, o come parte del carico di lavoro di **elaborazione e archiviazione dei dati** in visual studio 2017 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="027bb-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017 or later.</span></span>

- <span data-ttu-id="027bb-112">Il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="027bb-112">The Northwind sample database.</span></span> <span data-ttu-id="027bb-113">Per scaricare questo database di esempio, vedere la pagina di download dei [database di esempio per SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span><span class="sxs-lookup"><span data-stu-id="027bb-113">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="027bb-114">Attività della Guida rapida di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="027bb-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="027bb-115">Creare il servizio dati</span><span class="sxs-lookup"><span data-stu-id="027bb-115">Create the Data Service</span></span>](creating-the-data-service.md)

 <span data-ttu-id="027bb-116">Definire l'applicazione ASP.NET, definire il modello di dati, creare il servizio dati e abilitare l'accesso alle risorse.</span><span class="sxs-lookup"><span data-stu-id="027bb-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="027bb-117">Accedere al servizio da un Web browser</span><span class="sxs-lookup"><span data-stu-id="027bb-117">Access the Service from a Web Browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="027bb-118">Avviare il servizio da Visual Studio e accedervi inviando richieste GET HTTP attraverso un browser al feed esposto.</span><span class="sxs-lookup"><span data-stu-id="027bb-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="027bb-119">Creare l'applicazione client di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="027bb-119">Create the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="027bb-120">Creare un'app WPF per utilizzare il feed OData, associare dati a controlli Windows, modificare dati nei controlli associati e quindi inviare di nuovo le modifiche al servizio dati.</span><span class="sxs-lookup"><span data-stu-id="027bb-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="027bb-121">I file di progetto di una versione completa della guida rapida possono essere scaricati dalla pagina degli [esempi di documentazione di WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=179994) .</span><span class="sxs-lookup"><span data-stu-id="027bb-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="027bb-122">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="027bb-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="027bb-123">Avviare la Guida introduttiva</span><span class="sxs-lookup"><span data-stu-id="027bb-123">Start the quickstart</span></span>](creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="027bb-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="027bb-124">See also</span></span>

- [<span data-ttu-id="027bb-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="027bb-125">ADO.NET Entity Framework</span></span>](../adonet/ef/index.md)
