---
title: Esposizione dei dati come un servizio (WCF Data Services)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0c2d664166d9c0b750f6aecf9588a63b8705f0d1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="exposing-your-data-as-a-service-wcf-data-services"></a>Esposizione dei dati come un servizio (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]si integra con Visual Studio che consente di definire più facilmente i servizi per esporre i dati come [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed. Creazione di un servizio dati che espone un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed prevede i passaggi di base seguenti:  
  
1.  **Definire** **il modello di dati**. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]supporta in modo nativo i modelli di dati che si basano le [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md). Per ulteriori informazioni, vedere [procedura: creare un servizio dati tramite un'origine dati di ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
     [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] supporta inoltre i modelli di dati basati su oggetti CLR (Common Language Runtime) che restituiscono un'istanza dell'interfaccia <xref:System.Linq.IQueryable%601>. In questo modo è possibile distribuire servizi dati basati su elenchi, matrici e raccolte di .NET Framework. Per consentire l'esecuzione di operazioni di creazione, aggiornamento ed eliminazione su queste strutture di dati, è inoltre necessario implementare l'interfaccia <xref:System.Data.Services.IUpdatable>. Per ulteriori informazioni, vedere [procedura: creare un servizio dati tramite il Provider di Reflection](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).  
  
     Per scenari più avanzati, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] include un set di provider che consentono di definire un modello di dati in base ai tipi di dati ad associazione tardiva. Per ulteriori informazioni, vedere [provider di servizi dati personalizzati](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).  
  
2.  **Creare il servizio dati.** La maggior parte dei servizi di base espone una classe che eredita dalla classe <xref:System.Data.Services.DataService%601> , con un tipo `T` che corrisponde al nome completo dello spazio dei nomi del contenitore di entità. Per altre informazioni, vedere [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
3.  **Configurare il servizio dati.** Per impostazione predefinita, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] disabilita l'accesso alle risorse esposte da un contenitore di entità. L'interfaccia <xref:System.Data.Services.DataServiceConfiguration> consente di configurare l'accesso a risorse e operazioni del servizio, di specificare la versione supportata di [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] e di definire altri comportamenti a livello di server, ad esempio i comportamenti di invio in batch o il numero massimo di entità che è possibile restituire in un'unica risposta. Per ulteriori informazioni, vedere [configurazione del servizio dati](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Per un esempio di come creare un servizio dati semplice basato sul database di esempio Northwind, vedere [delle Guide rapide](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 [Panoramica](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)
