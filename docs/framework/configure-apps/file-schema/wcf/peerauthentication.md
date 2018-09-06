---
title: '&lt;peerAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: bb83d2badad609394a66246fc14c19a6602399e0
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43875989"
---
# <a name="ltpeerauthenticationgt"></a>&lt;peerAuthentication&gt;
Specifica le impostazioni di autenticazione di un certificato peer usato da un nodo peer.  
  
 \<system.ServiceModel>  
\<i comportamenti >  
\<serviceBehaviors>  
\<comportamento >  
\<serviceCredentials>  
\<peer >  
\<peerAuthentication>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<peerAuthentication  
      customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
      certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
      revocationMode="NoCheck/Online/Offline"  
      trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`certificateValidationMode`|Enumerazione facoltativa. Specifica una delle tre modalità usate per convalidare credenziali. L'attributo è di tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.|  
|`customCertificateValidatorType`|Stringa facoltativa. Specifica un tipo e un assembly usati per convalidare un tipo personalizzato. Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`. L'attributo è di tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Windows Communication Foundation (WCF) offre un peer predefinito validator del certificato che verifica il certificato peer a fronte dell'archivio persone attendibili. Verifica inoltre che il certificato sia concatenato a una radice valida. È possibile implementare una convalida personalizzata per specificare un comportamento diverso e usare questo attributo per puntare alla convalida personalizzata.|  
|`revocationMode`|Enumerazione facoltativa. Specifica la modalità di revoca dei certificati. L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>. Il sistema verifica che il certificato peer non sia stato revocato cercandolo nell'elenco dei certificati revocati. Questo controllo può essere eseguito controllando in linea o in un elenco di revoche memorizzato nella cache. È possibile disattivare il controllo di revoca impostando l'attributo su NoCheck.|  
|`trustedStoreLocation`|Enumerazione facoltativa. Specifica il percorso di archivio dati attendibile dove il certificato peer viene convalidato dal sistema di sicurezza WCF. L'attributo è di tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<peer >](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Specifica le credenziali correnti per un nodo peer.|  
  
## <a name="remarks"></a>Note  
 L'elemento `<authentication>` corrisponde alla classe <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>. Questo elemento specifica una convalida, che viene richiamata durante l'autenticazione tra peer adiacenti nella rete. Quando un nuovo peer tenta di stabilire una connessione con un peer adiacente, passa la propria credenziale al peer che risponde. Viene richiamata la convalida del risponditore per verificare la credenziale della parte remota. Ogni volta che viene stabilita una connessione peer nella rete, entrambi i peer vengono reciprocamente autenticati, indicando che vengono richiamati validator su entrambe le parti.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [Uso di certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Reti peer-to-peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [Autenticazione dei messaggi del canale peer](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [Autenticazione personalizzata del canale peer](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [Protezione di applicazioni del canale peer](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
