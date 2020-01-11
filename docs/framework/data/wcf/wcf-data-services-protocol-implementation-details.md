---
title: Dettagli di implementazione del protocollo WCF Data Services
ms.date: 03/30/2017
ms.assetid: 712d689b-fada-4cbb-bcdb-d65a3ef83b4c
ms.openlocfilehash: 2302b5577bec3fc4221bc6e5161c87905c38bec3
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900863"
---
# <a name="wcf-data-services-protocol-implementation-details"></a>Dettagli di implementazione del protocollo WCF Data Services
## <a name="odata-protocol-implementation-details"></a>Dettagli di implementazione del protocollo OData  
Il Open Data Protocol (OData) richiede che un servizio dati che implementa il protocollo fornisca un certo set minimo di funzionalità. Queste funzionalità sono descritte nei documenti del protocollo in termini di "should" e "must". Altre funzionalità facoltative sono descritte in termini di "May". In questo articolo vengono descritte le funzionalità facoltative che non sono attualmente implementate da WCF Data Services.
  
### <a name="support-for-the-format-query-option"></a>Supporto dell'opzione query $format  
 Il protocollo OData supporta sia la notazione JavaScript (JSON) sia i feed Atom, mentre OData fornisce l'opzione di query di sistema `$format` per consentire a un client di richiedere il formato del feed di risposta. Questa opzione query di sistema, se supportata dal servizio dati, deve eseguire l'override del valore dell'intestazione Accept della richiesta. WCF Data Services supporta la restituzione di feed JSON e Atom. Tuttavia, l'implementazione predefinita non supporta l'opzione query `$format` e usa solo il valore dell'intestazione Accept per determinare il formato della risposta. In alcuni casi è necessario che il servizio dati supporti l'opzione query `$format`, ad esempio quando i client non possono impostare l'intestazione Accept. Per supportare questi scenari, è necessario estendere il servizio dati per gestire questa opzione nell'URI. Per aggiungere questa funzionalità al servizio dati, scaricare il [JSONP e il supporto del formato controllato da URL per](https://go.microsoft.com/fwlink/?LinkId=208228) il progetto di esempio ADO.NET Data Services dal sito Web MSDN Code Gallery e aggiungerlo al progetto del servizio dati. Questo esempio rimuove l'opzione query `$format` e imposta l'intestazione Accept su `application/json`. Quando si include il progetto di esempio aggiungendo `JSONPSupportBehaviorAttribute` alla classe del servizio dati, si consente al servizio di gestire l'opzione query `$format``$format=json`. È necessario personalizzare ulteriormente questo progetto di esempio per gestire anche `$format=atom` o gli altri formati personalizzati.  
  
## <a name="wcf-data-services-behaviors"></a>Comportamenti di WCF Data Services  
 I seguenti comportamenti di WCF Data Services non sono definiti in modo esplicito dal protocollo OData:  
  
### <a name="default-sorting-behavior"></a>Comportamento di ordinamento predefinito  
 Quando una richiesta di query inviata al servizio dati include un'opzione query di sistema `$top` o `$skip` e non include l'opzione query di sistema `$orderby`, il feed restituito viene ordinato in base alle proprietà chiave in ordine crescente, poiché l'ordinamento è necessario per garantire il paging corretto dei risultati. A tale scopo, il servizio dati aggiunge un'espressione di ordinamento alla query. Questo comportamento si verifica anche quando viene abilitato il paging basato su server nel servizio dati. Per ulteriori informazioni, vedere [configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md). Per controllare l'ordinamento del feed restituito, è necessario includere `$orderby` nell'URI della query.  
  
## <a name="see-also"></a>Vedere anche

- [Definizione di WCF Data Services](defining-wcf-data-services.md)
- [Libreria client WCF Data Services](wcf-data-services-client-library.md)
