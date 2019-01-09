---
title: Elemento &lt;peerAuthentication&gt;
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 8937df6a2fcab305a519d566f7d666a3d94b4061
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149716"
---
# <a name="ltpeerauthenticationgt-element"></a>Elemento &lt;peerAuthentication&gt;
Specifica le opzioni di autenticazione dei client peer-to-peer.  
  
 Per altre informazioni sulla programmazione peer-to-peer, vedere [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
 \<system.ServiceModel>  
\<i comportamenti >  
\<endpointBehaviors >  
\<comportamento >  
\<clientCredentials>  
\<peer >  
\<peerAuthentication >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`customCertificateValidatorType`|Stringa facoltativa. Un tipo e un assembly usati per convalidare un tipo personalizzato. Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.|  
|`certifcateValidationMode`|Enumerazione facoltativa. Specifica una delle tre modalità usate per convalidare credenziali. Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`. Il valore predefinito è `ChainTrust`.|  
|`revocationMode`|Enumerazione facoltativa. Una delle modalità usate per verificare un elenco dei certificati revocati. Il valore predefinito è `Online`.|  
|`trustedStoreLocation`|Enumerazione facoltativa. Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`. Questo valore viene usato quando viene negoziato un certificato del servizio con il client. La convalida viene eseguita sul **persone attendibili** archiviare nel percorso dell'archivio specificato. Il valore predefinito è `CurrentUser`.|  
  
## <a name="customcertificatevalidatortype-attribute"></a>Attributo customCertificateValidatorType  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|String|Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo. Come minimo, sono necessari uno spazio dei nomi e un nome del tipo. Le informazioni facoltative comprendono il nome dell'assembly, il numero di versione, impostazioni cultura e token della chiave pubblica.|  
  
## <a name="certificatevalidationmode-attribute"></a>Attributo certificateValidationMode  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|Enumerazione|Uno dei valori seguenti: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`. Il valore predefinito è `ChainTrust`.<br /><br /> Per altre informazioni, vedere [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## <a name="revocationmode-attribute"></a>Attributo revocationMode  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|Enumerazione|Uno dei valori seguenti: `NoCheck`, `Online`, `Offline`. Il valore predefinito è `Online`.<br /><br /> Per altre informazioni, vedere [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>Attributo trustedStoreLocation  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|Enumerazione|Uno dei valori seguenti: `LocalMachine` o `CurrentUser`. Il valore predefinito è `CurrentUser`. Se l'applicazione client viene eseguita con un account di sistema, il certificato è generalmente situato in `LocalMachine`. Se l'applicazione client viene eseguita con un account utente, il certificato è generalmente situato in `CurrentUser`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<peer >](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|Specifica una credenziale usata per l'autenticazione del client con un servizio peer.|  
  
## <a name="remarks"></a>Note  
 L'elemento `<authentication>` corrisponde alla classe <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>. Questo elemento specifica una convalida, che viene richiamata durante l'autenticazione tra peer adiacenti nella rete. Quando un nuovo peer tenta di stabilire una connessione con un peer adiacente, passa la propria credenziale al peer che risponde. Viene richiamata la convalida del risponditore per verificare la credenziale della parte remota. Ogni volta che viene stabilita una connessione peer nella rete, entrambi i peer vengono reciprocamente autenticati, indicando che vengono richiamati validator su entrambe le parti.  
  
## <a name="example"></a>Esempio  
 Il codice seguente imposta la modalità di convalida del certificato su `PeerOrChainTrust`.  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <peerAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
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
