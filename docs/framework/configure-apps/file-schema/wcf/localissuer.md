---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 4ec5a99139112ae600c1c2bc44feb6d3f62da1e0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931731"
---
# <a name="localissuer"></a>\<> localIssuer
Specifica l'indirizzo e l'associazione dell'autorità emittente locale da usare per ottenere un token di sicurezza.  
  
 \<system.ServiceModel>  
\<comportamenti >  
sezione endpointBehaviors  
\<comportamento >  
\<clientCredentials>  
\<issuedToken>  
\<> localIssuer  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|Address|Stringa obbligatoria. Specifica l'URI dell'emittente locale.|  
|binding|Stringa facoltativa. Una delle associazioni fornite dal sistema Per un elenco, vedere [associazioni fornite dal sistema](../../../wcf/system-provided-bindings.md).|  
|bindingConfiguration|Stringa facoltativa. Specifica una configurazione di associazione presente nel file di configurazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Specifica informazioni sull'identità per l'autorità emittente locale.|  
|[\<intestazioni >](headers-element.md)|Raccolta di intestazioni di indirizzo richiesta per indirizzare correttamente l'autorità emittente locale. È possibile usare la parola chiave `add` per aggiungere un'intestazione a questa raccolta.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<issuedToken>](issuedtoken.md)|Specifica un token personalizzato usato per autenticare un client presso un servizio.|  
  
## <a name="remarks"></a>Note  
 Quando si ottiene un token rilasciato da un servizio token di sicurezza (STS, Security Token Service), l'applicazione client deve essere configurata con l'indirizzo da usare per comunicare con il servizio token di sicurezza. Quando non fornisce un URL per il servizio token di sicurezza o quando l'indirizzo dell'emittente di un'associazione federata è `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o `null`, il canale Windows Communication Foundation (WCF) del client usa i valori specificati da <xref:System.ServiceModel.WSFederationHttpBinding> `address` e`binding` per comunicare con il servizio token di servizio per ottenere il token emesso. Per ulteriori informazioni sulla configurazione di un'autorità emittente locale, [vedere Procedura: Configurare un'autorità emittente](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)locale.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono impostati gli attributi `address`, `binding` e `bindingConfiguration` di un elemento `localIssuer`.  
  
```xml  
<system.serviceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="MyEndpointBehavior">
        <clientCredentials>
          <issuedToken cacheIssuedTokens="false"
                       defaultKeyEntropyMode="ClientEntropy">
            <localIssuer address="net.tcp://cohowinery/tokens"
                         binding="netTcpBinding"
                         bindingConfiguration="myTcpBindingConfig" />
          </issuedToken>
        </clientCredentials>
      </behavior>
    </endpointBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [Comportamenti di sicurezza](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Procedura: Configurare un'autorità emittente locale](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Identità del servizio e autenticazione](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Comportamenti di sicurezza](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Federazione e token rilasciati](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Protezione di servizi e client](../../../wcf/feature-details/securing-services-and-clients.md)
- [Protezione di client](../../../wcf/securing-clients.md)
- [Procedura: Creazione di un client federato](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [Federazione e token rilasciati](../../../wcf/feature-details/federation-and-issued-tokens.md)
