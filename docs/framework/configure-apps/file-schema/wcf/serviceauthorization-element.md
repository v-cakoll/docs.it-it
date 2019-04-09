---
title: <serviceAuthorization> elemento
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: 7099c5eca9cf28624153a705e4e16136628214a2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157345"
---
# <a name="serviceauthorization-element"></a>\<serviceAuthorization > elemento
Specifica impostazioni che autorizzano accesso alle operazioni del servizio  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceAuthorization>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|impersonateCallerForAllOperations|Valore booleano che specifica se tutte le operazioni nel servizio rappresentano il chiamante. Il valore predefinito è `false`.<br /><br /> Quando un'operazione del servizio specifica rappresenta il chiamante, il contesto del thread viene commutato nel contesto del chiamante prima dell'esecuzione del servizio specificato.|  
|principalPermissionMode|Imposta l'entità di sicurezza usata per eseguire operazioni nel server. Sono inclusi i valori seguenti:<br /><br /> -None<br />-   UseWindowsGroups<br />-   UseAspNetRoles<br />-Custom<br /><br /> Il valore predefinito è UseWindowsGroups. Il valore è di tipo <xref:System.ServiceModel.Description.PrincipalPermissionMode>. Per altre informazioni sull'uso di questo attributo, vedere [come: Limitare l'accesso con la classe PrincipalPermissionAttribute](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).|  
|roleProviderName|Una stringa che specifica il nome del provider di ruoli che fornisce informazioni sui ruoli per un'applicazione di Windows Communication Foundation (WCF). Il valore predefinito è una stringa vuota.|  
|ServiceAuthorizationManagerType|Stringa che contiene il tipo di gestione autorizzazione del servizio. Per altre informazioni, vedere <xref:System.ServiceModel.ServiceAuthorizationManager>.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|authorizationPolicies|Contiene una raccolta di tipi di criteri di autorizzazione che possono essere aggiunti mediante la parola chiave `add`. Ciascun criterio di autorizzazione contiene un solo attributo `policyType` obbligatorio che è una stringa. L'attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni. Su questa base può essere concesso o negato il controllo di accesso. Per altre informazioni, vedere <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Contiene una raccolta di impostazioni per il comportamento di un servizio.|  
  
## <a name="remarks"></a>Note  
 Questa sezione contiene elementi che influiscono su autorizzazioni, provider del ruolo personalizzati e rappresentazioni.  
  
 L'attributo `principalPermissionMode` specifica i gruppi di utenti da usare quando si autorizza l'uso di un metodo protetto. Il valore predefinito è `UseWindowsGroups` e specifica che la ricerca degli ID che tentano di accedere a una determinata risorsa viene eseguita nei gruppi di Windows, ad esempio "Administrators" o "Users". È inoltre possibile specificare `UseAspNetRoles` usare un provider di ruoli personalizzato configurato nel \<System. Web > elemento, come illustrato nel codice seguente.  
  
```xml  
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
           type="System.Web.Security.SqlMembershipProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipProvider"
           enablePasswordRetrieval="false"
           enablePasswordReset="false"
           requiresQuestionAndAnswer="false"
           requiresUniqueEmail="true"
           passwordFormat="Hashed" />
    </providers>
  </membership>
  <!-- Other configuration code not shown. -->
</system.web>
```  
  
 Nell'esempio di codice seguente viene illustrato l'uso di un elemento `roleProviderName` con l'attributo `principalPermissionMode`.  
  
```xml  
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```  
  
 Per un esempio dettagliato dell'uso di questo elemento di configurazione, vedere [autorizzare l'accesso alle operazioni del servizio](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) e [criteri di autorizzazione](../../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [Comportamenti di sicurezza](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Autorizzazione dell'accesso alle operazioni del servizio](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [Procedura: Creare un gestore autorizzazioni personalizzato per un servizio](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [Procedura: Limitare l'accesso con la classe PrincipalPermissionAttribute](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [Criteri di autorizzazione](../../../../../docs/framework/wcf/samples/authorization-policy.md)
