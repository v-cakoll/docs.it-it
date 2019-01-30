---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: d8ca43a7b633d7d19dd37ceb0ff64075931b6c5c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254769"
---
# <a name="authorizationpolicies"></a>\<authorizationPolicies>
Questa sezione di configurazione contiene una raccolta di tipi di criteri di autorizzazione che possono essere aggiunti mediante la parola chiave `add`. Ciascun criterio di autorizzazione contiene un solo attributo `policyType` obbligatorio che è una stringa. L'attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni. Su questa base può essere concesso o negato il controllo di accesso. Per altre informazioni sul funzionamento dei criteri di autorizzazione, vedere <xref:System.IdentityModel.Policy.IAuthorizationPolicy> e [criteri di autorizzazione](../../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [Autorizzazione dell'accesso alle operazioni del servizio](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [Procedura: Creare un gestore autorizzazioni personalizzato per un servizio](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [Criteri di autorizzazione](../../../../../docs/framework/wcf/samples/authorization-policy.md)
