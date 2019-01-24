---
title: Provider Entity Framework (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
ms.openlocfilehash: 94a708ca33aa94c7a0143d195803d17d49be4bdb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569115"
---
# <a name="entity-framework-provider-wcf-data-services"></a>Provider Entity Framework (WCF Data Services)
Analogamente a [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], ADO.NET Entity Framework è basato su Entity Data Model, un tipo di modello entità-relazione. Entity Framework traduce le operazioni eseguite sulla relativa implementazione di Entity Data Model, che viene chiamato il *del modello concettuale*, in operazioni equivalenti su un'origine dati. Ciò rende Entity Framework il provider ideale per i servizi dati basati su dati relazionali, consentendo inoltre l'uso di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] da parte di qualsiasi database che disponga di un provider di dati con supporto per Entity Framework. Per un elenco delle origini dati che supportano attualmente Entity Framework, vedere [provider di terze parti per Entity Framework](https://go.microsoft.com/fwlink/?LinkId=143699).  
  
 In un modello concettuale il contenitore di entità rappresenta la radice del servizio. È necessario definire un modello concettuale in Entity Framework prima che i dati possano essere esposti da un servizio dati. Per altre informazioni, vedere [Procedura: Creare un servizio dati tramite un'origine dati ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] supporta il modello di concorrenza ottimistica consentendo la definizione di un token di concorrenza per un'entità. Questo token di concorrenza, che include una o più proprietà dell'entità, viene usato dal servizio dati per determinare se si è verificata una modifica nei dati richiesti, aggiornati o eliminati. Quando i valori del token ottenuti dal valore eTag nella richiesta sono diversi da quelli correnti dell'entità, viene generata un'eccezione dal servizio dati. Per indicare che una proprietà fa parte del token di concorrenza, è necessario applicare l'attributo `ConcurrencyMode="Fixed"` nel modello di dati definito dal provider di [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]. Il token di concorrenza non può includere una proprietà della chiave o una proprietà di navigazione. Per altre informazioni, vedere [aggiornamento del servizio dati](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 Per altre informazioni su Entity Framework, vedere [Panoramica di Entity Framework](../../../../docs/framework/data/adonet/ef/overview.md).  
  
## <a name="see-also"></a>Vedere anche
- [Provider di servizi dati](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [Provider di reflection](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
