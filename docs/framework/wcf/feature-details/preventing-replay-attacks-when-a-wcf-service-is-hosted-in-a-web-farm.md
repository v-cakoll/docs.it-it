---
title: Prevenzione degli attacchi di tipo "replay" quando un servizio WCF è ospitato in una Web farm
ms.date: 03/30/2017
ms.assetid: 1c2ed695-7a31-4257-92bd-9e9731b886a5
ms.openlocfilehash: b0e52624ef4483672abd8cd0995dbc2e58f95ca1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684866"
---
# <a name="preventing-replay-attacks-when-a-wcf-service-is-hosted-in-a-web-farm"></a>Prevenzione degli attacchi di tipo "replay" quando un servizio WCF è ospitato in una Web farm
Quando si utilizza la sicurezza dei messaggi. in WCF si impediscono attacchi di tipo replay creando un parametro NONCE in base al messaggio in arrivo e controllando l'oggetto `InMemoryNonceCache` interno per verificare se il parametro NONCE generato è presente. In tal caso, il messaggio viene rimosso come di tipo replay. Quando un servizio WCF viene ospitato in una Web farm, poiché `InMemoryNonceCache` non viene condiviso tra i nodi della Web farm, il servizio è vulnerabile agli attacchi di tipo replay.  Per attenuare questo scenario, WCF 4.5 fornisce un punto di estendibilità che consente di implementare la propria cache NONCE condivisa derivando una classe dalla classe astratta <xref:System.ServiceModel.Security.NonceCache>.  
  
## <a name="noncecache-implementation"></a>Implementazione NonceCache  
 Per implementare la propria cache NONCE condivisa, derivare una classe da <xref:System.ServiceModel.Security.NonceCache> ed eseguire l'override dei metodi <xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> e <xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A>. <xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> controllerà se il parametro NONCE specificato esiste nella cache. <xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A> tenterà di aggiungere un parametro NONCE alla cache. Una volta implementata, la classe viene associata creando un'istanza e assegnandola a <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.NonceCache%2A> per il rilevamento di attacchi di tipo replay lato client e a <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NonceCache%2A> per il rilevamento di attacchi di tipo replay lato server. Non esiste alcun supporto di configurazione predefinito per questa funzionalità.  
  
## <a name="see-also"></a>Vedere anche
- [Sicurezza dei messaggi](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)
- [SymmetricSecurityBindingElement](../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)
