---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: ebe976df9af0c316e95a1e089412e57a575a6df1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157235"
---
# <a name="clientcredentials"></a>\<clientCredentials>
Specifica le credenziali usate per autenticare il client presso un servizio.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<clientCredentials>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<clientCredentials type="String"
                   supportInteractive="Boolean" >
  <clientCertificate>
  </clientCertificate>
  <digest>
  </digest>
  <isuedToken>
  </isuedToken>
  <peer>
  </peer>
  <serviceCertificate>
  </serviceCertificate>
  <windowsAuthentication>
  </windowsAuthentication>
</clientCredentials>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`supportInteractive`|Valore booleano che specifica se un utente interattivo può essere coinvolto nella selezione di una credenziale client in fase di esecuzione. Il valore predefinito è `true`.|  
|`type`|Stringa che specifica il tipo di questo elemento di configurazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<clientCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|Specifica il certificato usato per autenticare il client presso il servizio. L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.|  
|[\<httpDigest>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|Specifica un digest usato per autenticare il client presso il servizio. L'elemento è di tipo <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.|  
|[\<issuedToken>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Specifica un tipo di token personalizzato usato per autenticare il client presso un servizio token di sicurezza (STS, Secure Token Service). L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.|  
|[\<peer>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|Specifica una credenziale peer corrente. L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.|  
|[\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|Specifica il certificato usato per autenticare il servizio presso il client e fornisce una struttura per l'impostazione delle opzioni del certificato. Questo certificato deve essere fornito fuori banda dal servizio al client. L'elemento è di tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.|  
|[\<windows>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|Specifica una credenziale Windows. Il valore predefinito è la credenziale del thread corrente. L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsClientElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Specifica un comportamento dell'endpoint.|  
  
## <a name="remarks"></a>Note  
 Le credenziali client sono usate per autenticare i client presso i servizi nei casi in cui non è richiesta l'autenticazione reciproca. È inoltre possibile usare questa sezione di configurazione per specificare i certificati di servizio negli scenari in cui il client deve usare il certificato di un servizio per proteggere i messaggi inviati a un servizio.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [Comportamenti di sicurezza](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Protezione di client](../../../../../docs/framework/wcf/securing-clients.md)
