---
title: Dettagli di implementazione del protocollo WCF Data Services
ms.date: 03/30/2017
ms.assetid: 712d689b-fada-4cbb-bcdb-d65a3ef83b4c
ms.openlocfilehash: 1cd4204d9e1626ac45bccf3954fdaf1c156af7f8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779651"
---
# <a name="wcf-data-services-protocol-implementation-details"></a>Dettagli di implementazione del protocollo WCF Data Services
## <a name="odata-protocol-implementation-details"></a>Dettagli di implementazione del protocollo OData  
 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] richiede che un servizio dati che implementa il protocollo fornisca un determinato set di funzionalità minimo. Queste funzionalità sono descritte nei documenti del protocollo in termini di "should" e "must". Altre funzionalità facoltative sono descritte in termini di "maggio". In questo argomento vengono descritte tali funzionalità facoltative che non sono attualmente implementate da [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Per ulteriori informazioni, vedere la [documentazione del protocollo OData](https://go.microsoft.com/fwlink/?LinkID=184554).  
  
### <a name="support-for-the-format-query-option"></a>Supporto dell'opzione query $format  
 Il protocollo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] supporta i feed JSON (JavaScript Notation) e Atom e [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fornisce l'opzione query di sistema `$format` per consentire a un client di richiedere il formato del feed di risposta. Questa opzione query di sistema, se supportata dal servizio dati, deve eseguire l'override del valore dell'intestazione Accept della richiesta. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] supporta la restituzione dei feed JSON e Atom. Tuttavia, l'implementazione predefinita non supporta l'opzione query `$format` e usa solo il valore dell'intestazione Accept per determinare il formato della risposta. In alcuni casi è necessario che il servizio dati supporti l'opzione query `$format`, ad esempio quando i client non possono impostare l'intestazione Accept. Per supportare questi scenari, è necessario estendere il servizio dati per gestire questa opzione nell'URI. Per aggiungere questa funzionalità al servizio dati, scaricare il [JSONP e il supporto del formato controllato da URL per](https://go.microsoft.com/fwlink/?LinkId=208228) il progetto di esempio ADO.NET Data Services dal sito Web MSDN Code Gallery e aggiungerlo al progetto del servizio dati. Questo esempio rimuove l'opzione query `$format` e imposta l'intestazione Accept su `application/json`. Quando si include il progetto di esempio aggiungendo `JSONPSupportBehaviorAttribute` alla classe del servizio dati, si consente al servizio di gestire l'opzione query `$format``$format=json`. È necessario personalizzare ulteriormente questo progetto di esempio per gestire anche `$format=atom` o gli altri formati personalizzati.  
  
## <a name="wcf-data-services-behaviors"></a>Comportamenti di WCF Data Services  
 I comportamenti di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] seguenti non sono definiti in modo esplicito dal protocollo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]:  
  
### <a name="default-sorting-behavior"></a>Comportamento di ordinamento predefinito  
 Quando una richiesta di query inviata al servizio dati include un'opzione query di sistema `$top` o `$skip` e non include l'opzione query di sistema `$orderby`, il feed restituito viene ordinato in base alle proprietà chiave in ordine crescente, poiché l'ordinamento è necessario per garantire il paging corretto dei risultati. A tale scopo, il servizio dati aggiunge un'espressione di ordinamento alla query. Questo comportamento si verifica anche quando viene abilitato il paging basato su server nel servizio dati. Per ulteriori informazioni, vedere [configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md). Per controllare l'ordinamento del feed restituito, è necessario includere `$orderby` nell'URI della query.  
  
## <a name="see-also"></a>Vedere anche

- [Definizione di WCF Data Services](defining-wcf-data-services.md)
- [Libreria client WCF Data Services](wcf-data-services-client-library.md)
