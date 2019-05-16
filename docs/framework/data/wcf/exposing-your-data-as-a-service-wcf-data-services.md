---
title: Esposizione dei dati come un servizio (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
ms.openlocfilehash: 0d774db264a02d8d6c752f55344ec1ab6645c0bb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633657"
---
# <a name="expose-your-data-as-a-service-wcf-data-services"></a>Esporre i dati come servizio (WCF Data Services)

WCF Data Services si integra con Visual Studio che consentono di definire con facilità i servizi per l'esposizione dei dati come [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed. La creazione di un servizio dati che espone un feed OData prevede i passaggi di base seguenti:

1. **Definire il modello di dati.** WCF Data Services supporta in modo nativo i modelli di dati basati sul [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md). Per altre informazioni, vedere [Procedura: Creare un servizio dati tramite un'origine dati ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).

     WCF Data Services supporta inoltre i modelli di dati basati su oggetti common language runtime (CLR) che restituiscono un'istanza di <xref:System.Linq.IQueryable%601> interfaccia. In questo modo è possibile distribuire servizi dati basati su elenchi, matrici e raccolte di .NET Framework. Per consentire l'esecuzione di operazioni di creazione, aggiornamento ed eliminazione su queste strutture di dati, è inoltre necessario implementare l'interfaccia <xref:System.Data.Services.IUpdatable>. Per altre informazioni, vedere [Procedura: Creare un servizio dati tramite il Provider di Reflection](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).

     Per scenari più avanzati, WCF Data Services include un set di provider che consentono di definire un modello di dati basato su tipi di dati con associazione tardiva. Per altre informazioni, vedere [provider di servizi dati personalizzati](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).

2. **Creare il servizio dati.** La maggior parte dei servizi di base espone una classe che eredita dalla classe <xref:System.Data.Services.DataService%601> , con un tipo `T` che corrisponde al nome completo dello spazio dei nomi del contenitore di entità. Per altre informazioni, vedere [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).

3. **Configurazione del servizio dati.** Per impostazione predefinita, WCF Data Services disabilita l'accesso alle risorse esposte da un contenitore di entità. Il <xref:System.Data.Services.DataServiceConfiguration> interfaccia consente di configurare l'accesso alle risorse e operazioni del servizio, specificare la versione supportata di OData e per definire altri comportamenti a livello di servizio, ad esempio il numero massimo di entità che possono essere restituiti o comportamenti di invio in batch in un'unica risposta. Per altre informazioni, vedere [configurazione del servizio dati](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).

Per un esempio di come creare un servizio dati semplice basato sul database di esempio Northwind, vedere [Guida introduttiva](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).

## <a name="see-also"></a>Vedere anche

- [Introduzione](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
- [Panoramica](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)
