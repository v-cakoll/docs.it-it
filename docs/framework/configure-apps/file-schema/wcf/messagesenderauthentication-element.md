---
title: Elemento <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: bab0e50d7feba3ea55d505be07cfa41427a5cbbc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397780"
---
# <a name="messagesenderauthentication-element"></a>Elemento \<messageSenderAuthentication>
Specifica opzioni di autenticazione per i mittenti di messaggi peer-to-peer.  
  
 Per ulteriori informazioni sulla programmazione peer-to-peer, vedere la pagina relativa [alla rete peer-to-peer](../../../wcf/feature-details/peer-to-peer-networking.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`customCertificateValidatorType`|Un tipo e un assembly usati per convalidare un tipo personalizzato. Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.|  
|`certificateValidationMode`|Specifica una delle tre modalità usate per convalidare credenziali. Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.|  
|`revocationMode`|Una delle modalità usate per verificare un elenco dei certificati revocati.|  
|`trustedStoreLocation`|Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`. Questo valore viene usato quando viene negoziato un certificato del servizio con il client. La convalida viene eseguita sull'archivio **persone attendibili** nel percorso di archiviazione specificato.|  
  
## <a name="customcertificatevalidatortype-attribute"></a>Attributo customCertificateValidatorType  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|string|Facoltativo. Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo. Come minimo, sono necessari uno spazio dei nomi e un nome del tipo. Le informazioni facoltative comprendono il nome dell'assembly, il numero di versione, impostazioni cultura e token della chiave pubblica.|  
  
## <a name="certificatevalidationmode-attribute"></a>Attributo certificateValidationMode  
  
|Valore|Description|  
|-----------|-----------------|  
|Enumerazione|Facoltativa. Uno dei valori seguenti: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`. Il valore predefinito è `ChainTrust`. Il valore predefinito è `ChainTrust`.<br /><br /> Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="revocationmode-attribute"></a>Attributo revocationMode  
  
|Valore|Description|  
|-----------|-----------------|  
|Enumerazione|Uno dei valori seguenti: `NoCheck`, `Online`, `Offline`. Il valore predefinito è `Online`.<br /><br /> Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>Attributo trustedStoreLocation  
  
|Valore|Description|  
|-----------|-----------------|  
|Enumerazione|Uno dei valori seguenti: `LocalMachine` o `CurrentUser`. Il valore predefinito è `CurrentUser`. Se l'applicazione client viene eseguita con un account di sistema, il certificato è generalmente situato in `LocalMachine`. Se l'applicazione client viene eseguita con un account utente, il certificato è generalmente situato in `CurrentUser`. Il valore predefinito è `CurrentUser`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|Specifica una credenziale usata per l'autenticazione del client con un servizio peer.|  
  
## <a name="remarks"></a>Commenti  
 Se è stata scelta l'autenticazione dei messaggi, sarà necessario configurare questo elemento. Per i canali di output, ogni messaggio viene firmato utilizzando il certificato fornito da [\<certificate>](certificate-element.md) . Prima che vengano recapitati all'applicazione, tutti i messaggi vengono controllati a fronte delle credenziali del messaggio usando la convalida specificata dall'attributo `customCertificateValidatorType` di questo elemento. La convalida può accettare o rifiutare la credenziale.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice riportato di seguito viene impostata la modalità di convalida del mittente del messaggio su `PeerOrChainTrust`.  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)
- [Rete peer-to-peer](../../../wcf/feature-details/peer-to-peer-networking.md)
- [Autenticazione dei messaggi del canale peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Autenticazione personalizzata dei messaggi del canale](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Protezione di applicazioni del canale peer](../../../wcf/feature-details/securing-peer-channel-applications.md)
