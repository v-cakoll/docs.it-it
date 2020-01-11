---
title: Guida rapida (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: 43cd34ad02f1e2d212ff5e2ff4694591fbed52e5
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900952"
---
# <a name="quickstart-wcf-data-services"></a>Guida rapida (WCF Data Services)

Questa Guida introduttiva consente di acquisire familiarità con WCF Data Services e il Open Data Protocol (OData) tramite una serie di attività che supportano gli argomenti in [Introduzione](getting-started-with-wcf-data-services.md).

## <a name="what-youll-learn"></a>Che cosa apprenderai

Nella prima attività di questa Guida introduttiva viene illustrato come creare un servizio dati per esporre un feed OData dal database di esempio Northwind. Negli argomenti successivi, sarà possibile accedere al feed OData utilizzando un Web browser e creare anche un'applicazione client Windows Presentation Foundation (WPF) che utilizza il feed OData utilizzando le librerie client.

## <a name="prerequisites"></a>Prerequisiti

Per completare le attività incluse nella guida rapida, è necessario installare i componenti seguenti:

- Visual Studio

- Istanza di SQL Server. Sono inclusi SQL Server Express, incluso in un'installazione predefinita di Visual Studio 2015, o come parte del carico di lavoro di **elaborazione e archiviazione dei dati** in visual studio 2017 o versione successiva.

- Il database di esempio Northwind. Per scaricare questo database di esempio, vedere la pagina di download dei [database di esempio per SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).

## <a name="wcf-data-services-quickstart-tasks"></a>Attività della Guida rapida di WCF Data Services

 [Creare il servizio dati](creating-the-data-service.md)

 Definire l'applicazione ASP.NET, definire il modello di dati, creare il servizio dati e abilitare l'accesso alle risorse.

 [Accedere al servizio da un Web browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 Avviare il servizio da Visual Studio e accedervi inviando richieste GET HTTP attraverso un browser al feed esposto.

 [Creare l'applicazione client di .NET Framework](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 Creare un'app WPF per utilizzare il feed OData, associare dati a controlli Windows, modificare dati nei controlli associati e quindi inviare di nuovo le modifiche al servizio dati.

> [!NOTE]
> I file di progetto di una versione completa della Guida introduttiva possono essere scaricati da [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Avviare la Guida introduttiva](creating-the-data-service.md)

## <a name="see-also"></a>Vedere anche

- [ADO.NET Entity Framework](../adonet/ef/index.md)
