---
title: Dettagli di implementazione del protocollo WCF Data Services
ms.date: 03/30/2017
ms.assetid: 712d689b-fada-4cbb-bcdb-d65a3ef83b4c
ms.openlocfilehash: 1d68e278fbac0137d1a5b2dca2daedba2294a7ee
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2018
ms.locfileid: "44364415"
---
# <a name="wcf-data-services-protocol-implementation-details"></a>Dettagli di implementazione del protocollo WCF Data Services
## <a name="odata-protocol-implementation-details"></a>Dettagli di implementazione del protocollo OData  
 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] richiede che un servizio dati che implementa il protocollo fornisca un determinato set di funzionalità minimo. Queste funzionalità sono descritte nei documenti del protocollo in termini di "should" e "must". Altre funzionalità facoltative vengono descritte in termini di "may". In questo argomento vengono descritte tali funzionalità facoltative che non sono attualmente implementate da [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Per altre informazioni, vedere [documentazione del protocollo OData](https://go.microsoft.com/fwlink/?LinkID=184554).  
  
### <a name="support-for-the-format-query-option"></a>Supporto dell'opzione query $format  
 Il protocollo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] supporta i feed JSON (JavaScript Notation) e Atom e [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fornisce l'opzione query di sistema `$format` per consentire a un client di richiedere il formato del feed di risposta. Questa opzione query di sistema, se supportata dal servizio dati, deve eseguire l'override del valore dell'intestazione Accept della richiesta. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] supporta la restituzione dei feed JSON e Atom. Tuttavia, l'implementazione predefinita non supporta l'opzione query `$format` e usa solo il valore dell'intestazione Accept per determinare il formato della risposta. In alcuni casi è necessario che il servizio dati supporti l'opzione query `$format`, ad esempio quando i client non possono impostare l'intestazione Accept. Per supportare questi scenari, è necessario estendere il servizio dati per gestire questa opzione nell'URI. È possibile aggiungere questa funzionalità al servizio dati scaricando il [controllata dall'URL del formato JSONP e supporto per ADO.NET Data Services](https://go.microsoft.com/fwlink/?LinkId=208228) progetto di esempio dal sito web MSDN Code Gallery e aggiungerlo al progetto di servizio dati. Questo esempio rimuove l'opzione query `$format` e imposta l'intestazione Accept su `application/json`. Quando si include il progetto di esempio aggiungendo `JSONPSupportBehaviorAttribute` alla classe del servizio dati, si consente al servizio di gestire l'opzione query `$format``$format=json`. È necessario personalizzare ulteriormente questo progetto di esempio per gestire anche `$format=atom` o gli altri formati personalizzati.  
  
## <a name="wcf-data-services-behaviors"></a>Comportamenti di WCF Data Services  
 I comportamenti di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] seguenti non sono definiti in modo esplicito dal protocollo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]:  
  
### <a name="default-sorting-behavior"></a>Comportamento di ordinamento predefinito  
 Quando una richiesta di query inviata al servizio dati include un'opzione query di sistema `$top` o `$skip` e non include l'opzione query di sistema `$orderby`, il feed restituito viene ordinato in base alle proprietà chiave in ordine crescente, poiché l'ordinamento è necessario per garantire il paging corretto dei risultati. A tale scopo, il servizio dati aggiunge un'espressione di ordinamento alla query. Questo comportamento si verifica anche quando viene abilitato il paging basato su server nel servizio dati. Per altre informazioni, vedere [configurazione del servizio dati](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md). Per controllare l'ordinamento del feed restituito, è necessario includere `$orderby` nell'URI della query.  
  
## <a name="see-also"></a>Vedere anche  
 [Definizione di WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
