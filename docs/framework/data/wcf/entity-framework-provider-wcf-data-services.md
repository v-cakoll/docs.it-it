---
title: Provider Entity Framework (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
ms.openlocfilehash: 0b75e9645f05e5e83ff76cc138ee37e90600769a
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569258"
---
# <a name="entity-framework-provider-wcf-data-services"></a>Provider Entity Framework (WCF Data Services)
Come WCF Data Services, il Entity Framework ADO.NET è basato sul Entity Data Model, che è un tipo di modello entità-relazione. Il Entity Framework converte le operazioni sulla relativa implementazione del Entity Data Model, denominato *modello concettuale*, in operazioni equivalenti su un'origine dati. In questo modo il Entity Framework un provider ideale per i servizi dati basati su dati relazionali e qualsiasi database che disponga di un provider di dati che supporta l'Entity Framework può essere utilizzato con WCF Data Services. Per un elenco delle origini dati che attualmente supportano il Entity Framework, vedere [provider di terze parti per l'Entity Framework](https://go.microsoft.com/fwlink/?LinkId=143699).  
  
 In un modello concettuale il contenitore di entità rappresenta la radice del servizio. È necessario definire un modello concettuale in Entity Framework prima che i dati possano essere esposti da un servizio dati. Per altre informazioni, vedere [procedura: creare un servizio dati usando un'origine dati ADO.NET Entity Framework](create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
 WCF Data Services supporta il modello di concorrenza ottimistica consentendo di definire un token di concorrenza per un'entità. Questo token di concorrenza, che include una o più proprietà dell'entità, viene usato dal servizio dati per determinare se si è verificata una modifica nei dati richiesti, aggiornati o eliminati. Quando i valori del token ottenuti dal valore eTag nella richiesta sono diversi da quelli correnti dell'entità, viene generata un'eccezione dal servizio dati. Per indicare che una proprietà fa parte del token di concorrenza, è necessario applicare l'attributo `ConcurrencyMode="Fixed"` nel modello di dati definito dal provider di Entity Framework. Il token di concorrenza non può includere una proprietà della chiave o una proprietà di navigazione. Per ulteriori informazioni, vedere [aggiornamento del servizio dati](updating-the-data-service-wcf-data-services.md).  
  
 Per altre informazioni sulla Entity Framework, vedere [Panoramica di Entity Framework](../adonet/ef/overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Provider di servizi dati](data-services-providers-wcf-data-services.md)
- [Provider di reflection](reflection-provider-wcf-data-services.md)
- [Entity Data Model](../adonet/entity-data-model.md)
