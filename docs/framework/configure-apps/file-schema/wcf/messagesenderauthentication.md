---
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: 4749aeebedd9f918c2ed1a119767681f4c3ded37
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263667"
---
# <a name="messagesenderauthentication"></a>\<messageSenderAuthentication>
Specifica impostazioni di autenticazione per certificato peer usato dal mittente di un messaggio.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceCredentials>  
\<peer>  
\<messageSenderAuthentication>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`certificateValidationMode`|Enumerazione facoltativa. Specifica una delle cinque modalità usate per convalidare credenziali. L'attributo è di tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.|  
|`customCertificateValidatorType`|Stringa facoltativa. Specifica un tipo e un assembly usati per convalidare un tipo personalizzato. Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`. L'attributo è di tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Windows Communication Foundation (WCF) offre un peer predefinito validator del certificato che verifica il certificato peer a fronte dell'archivio persone attendibili. Verifica inoltre che il certificato sia concatenato a una radice valida. È possibile implementare una convalida personalizzata per specificare un comportamento diverso e usare questo attributo per puntare alla convalida personalizzata.|  
|`revocationMode`|Enumerazione facoltativa. Specifica la modalità di revoca dei certificati. L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>. Il sistema verifica che il certificato peer non sia stato revocato cercandolo nell'elenco dei certificati revocati. Questo controllo può essere eseguito controllando in linea o in un elenco di revoche memorizzato nella cache. È possibile disattivare il controllo di revoca impostando l'attributo su NoCheck.|  
|`trustedStoreLocation`|Enumerazione facoltativa. Specifica il percorso di archivio dati attendibile dove il certificato peer viene convalidato dal sistema di sicurezza WCF. L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<peer>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Specifica le credenziali correnti per un nodo peer.|  
  
## <a name="remarks"></a>Note  
 Se è stata scelta l'autenticazione dei messaggi, sarà necessario configurare questo elemento. Per i canali di output, ogni messaggio viene firmato utilizzando il certificato fornito dalla [ \<certificato >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md). Prima che vengano recapitati all'applicazione, tutti i messaggi vengono controllati a fronte delle credenziali del messaggio usando la convalida specificata dall'attributo `customCertificateValidatorType` di questo elemento. La convalida può accettare o rifiutare la credenziale.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [Uso di certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Reti peer-to-peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [Autenticazione dei messaggi del canale peer](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)
- [Autenticazione personalizzata del canale peer](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)
- [Protezione di applicazioni del canale peer](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
