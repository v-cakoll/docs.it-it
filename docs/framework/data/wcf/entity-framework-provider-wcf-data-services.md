---
title: Provider Entity Framework (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
ms.openlocfilehash: 612888aaa11c606112527f01864897560061845f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790844"
---
# <a name="entity-framework-provider-wcf-data-services"></a>Provider Entity Framework (WCF Data Services)
Analogamente a [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], ADO.NET Entity Framework è basato su Entity Data Model, un tipo di modello entità-relazione. Il Entity Framework converte le operazioni sulla relativa implementazione del Entity Data Model, denominato *modello concettuale*, in operazioni equivalenti su un'origine dati. Ciò rende Entity Framework il provider ideale per i servizi dati basati su dati relazionali, consentendo inoltre l'uso di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] da parte di qualsiasi database che disponga di un provider di dati con supporto per Entity Framework. Per un elenco delle origini dati che attualmente supportano il Entity Framework, vedere [provider di terze parti per l'Entity Framework](https://go.microsoft.com/fwlink/?LinkId=143699).  
  
 In un modello concettuale il contenitore di entità rappresenta la radice del servizio. È necessario definire un modello concettuale in Entity Framework prima che i dati possano essere esposti da un servizio dati. Per altre informazioni, vedere [Procedura: Creare un servizio dati utilizzando un'origine](create-a-data-service-using-an-adonet-ef-data-wcf.md)dati Entity Framework ADO.NET.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]supporta il modello di concorrenza ottimistica consentendo di definire un token di concorrenza per un'entità. Questo token di concorrenza, che include una o più proprietà dell'entità, viene usato dal servizio dati per determinare se si è verificata una modifica nei dati richiesti, aggiornati o eliminati. Quando i valori del token ottenuti dal valore eTag nella richiesta sono diversi da quelli correnti dell'entità, viene generata un'eccezione dal servizio dati. Per indicare che una proprietà fa parte del token di concorrenza, è necessario applicare l'attributo `ConcurrencyMode="Fixed"` nel modello di dati definito dal provider di [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]. Il token di concorrenza non può includere una proprietà della chiave o una proprietà di navigazione. Per ulteriori informazioni, vedere [aggiornamento del servizio dati](updating-the-data-service-wcf-data-services.md).  
  
 Per altre informazioni sulla Entity Framework, vedere [Panoramica di Entity Framework](../adonet/ef/overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Provider di servizi dati](data-services-providers-wcf-data-services.md)
- [Provider di reflection](reflection-provider-wcf-data-services.md)
- [Entity Data Model](../adonet/entity-data-model.md)
