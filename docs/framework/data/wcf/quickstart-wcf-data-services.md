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
# <a name="quickstart-wcf-data-services"></a>Guida rapida (WCF Data Services)

Questa guida introduttiva consente di acquisire familiarità con WCF Data ServicesWCF Data Services e il protocollo OData (Open Data Protocol) tramite una serie di attività che supportano gli argomenti in [Guida introduttiva](getting-started-with-wcf-data-services.md).

## <a name="what-youll-learn"></a>Contenuto dell'esercitazione

Nella prima attività di questa guida introduttiva viene illustrato come creare un servizio dati per esporre un feed OData dal database di esempio Northwind. Negli argomenti successivi si accederà al feed OData utilizzando un browser Web e si creerà anche un'applicazione client Windows Presentation Foundation (WPF) che utilizza il feed OData utilizzando le librerie client.

## <a name="prerequisites"></a>Prerequisiti

Per completare questa guida introduttiva, installare i componenti seguenti:

- Visual Studio

- Istanza di SQL Server. Ciò include SQL Server Express, incluso in un'installazione predefinita di Visual Studio 2015 o come parte del carico di lavoro di **archiviazione ed elaborazione** dei dati in Visual Studio 2017 o versione successiva.

- Il database di esempio Northwind. Per installare il database, eseguire lo script Transact-SQL da [Northwind e pubs database di esempio per Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).

## <a name="wcf-data-services-quickstart-tasks"></a>Attività introduttive dei servizi dati WCFWCF data services quickstart tasks

 [Creare il servizio datiCreate the Data Service](creating-the-data-service.md)

 Definire l'applicazione ASP.NET, definire il modello di dati, creare il servizio dati e abilitare l'accesso alle risorse.

 [Accedere al servizio da un browser Web](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 Avviare il servizio da Visual Studio e accedervi inviando richieste GET HTTP attraverso un browser al feed esposto.

 [Creare l'applicazione client .NET FrameworkCreate the .NET Framework Client Application](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 Creare un'app WPF per usare il feed OData, associare dati ai controlli Windows, modificare i dati nei controlli associati e quindi inviare le modifiche al servizio dati.

> [!NOTE]
> I file di progetto da una versione completata della guida introduttiva possono essere scaricati da [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Avviare la guida introduttiva](creating-the-data-service.md)

## <a name="see-also"></a>Vedere anche

- [ADO.NET Entity Framework](../adonet/ef/index.md)
