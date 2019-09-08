---
title: Esposizione dei dati come un servizio (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
ms.openlocfilehash: 1dc1f0ec12c50c4c97b141a34b468e3367ead75e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780309"
---
# <a name="expose-your-data-as-a-service-wcf-data-services"></a>Esporre i dati come servizio (WCF Data Services)

WCF Data Services si integra con Visual Studio per consentire di definire più facilmente i servizi per esporre i dati come [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed. La creazione di un servizio dati che espone un feed OData prevede i passaggi di base seguenti:

1. **Definire il modello di dati.** WCF Data Services supporta in modo nativo i modelli di dati basati sul [Entity Framework ADO.NET](../adonet/ef/index.md). Per altre informazioni, vedere [Procedura: Creare un servizio dati utilizzando un'origine](create-a-data-service-using-an-adonet-ef-data-wcf.md)dati Entity Framework ADO.NET.

     WCF Data Services supporta inoltre i modelli di dati basati su oggetti Common Language Runtime (CLR) che restituiscono un'istanza dell' <xref:System.Linq.IQueryable%601> interfaccia. In questo modo è possibile distribuire servizi dati basati su elenchi, matrici e raccolte di .NET Framework. Per consentire l'esecuzione di operazioni di creazione, aggiornamento ed eliminazione su queste strutture di dati, è inoltre necessario implementare l'interfaccia <xref:System.Data.Services.IUpdatable>. Per altre informazioni, vedere [Procedura: Creazione di un servizio dati tramite il provider](create-a-data-service-using-rp-wcf-data-services.md)di Reflection.

     Per scenari più avanzati, WCF Data Services include un set di provider che consentono di definire un modello di dati basato su tipi di dati ad associazione tardiva. Per ulteriori informazioni, vedere [provider di servizi dati personalizzati](custom-data-service-providers-wcf-data-services.md).

2. **Creazione del servizio dati.** La maggior parte dei servizi di base espone una classe che eredita dalla classe <xref:System.Data.Services.DataService%601> , con un tipo `T` che corrisponde al nome completo dello spazio dei nomi del contenitore di entità. Per altre informazioni, vedere [Defining WCF Data Services](defining-wcf-data-services.md).

3. **Configurare il servizio dati.** Per impostazione predefinita, WCF Data Services Disabilita l'accesso alle risorse esposte da un contenitore di entità. L' <xref:System.Data.Services.DataServiceConfiguration> interfaccia consente di configurare l'accesso a risorse e operazioni del servizio, di specificare la versione supportata di OData e di definire altri comportamenti a livello di servizio, ad esempio i comportamenti di invio in batch o il numero massimo di entità che possono essere restituite. in una singola risposta. Per ulteriori informazioni, vedere [configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md).

Per un esempio di come creare un servizio dati semplice basato sul database Northwind di esempio, vedere [Guida introduttiva](quickstart-wcf-data-services.md).

## <a name="see-also"></a>Vedere anche

- [Introduzione](getting-started-with-wcf-data-services.md)
- [Panoramica](wcf-data-services-overview.md)
