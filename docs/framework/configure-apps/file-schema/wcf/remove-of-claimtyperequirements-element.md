---
title: Elemento &lt;remove&gt; di &lt;claimTypeRequirements&gt;
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 33c6b935bb8d39f05e26646d4731ce1459beba81
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702145"
---
# <a name="ltremovegt-of-ltclaimtyperequirementsgt-element"></a>Elemento &lt;remove&gt; di &lt;claimTypeRequirements&gt;
Specifica i tipi di attestazioni da rimuovere nella credenziale federativa.  
  
 \<system.ServiceModel>  
\<le associazioni >  
\<wsFederatedBinding>  
\<binding>  
\<security>  
\<messaggio >  
\<claimTypeRequirements>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|claimType|URI che definisce il tipo di un'attestazione da rimuovere.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|Specifica una raccolta di tipi di attestazione obbligatori. Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.<br /><br /> In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso. Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni. Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
