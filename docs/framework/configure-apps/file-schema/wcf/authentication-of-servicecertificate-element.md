---
title: "&lt;authentication&gt; dell'elemento &lt;serviceCertificate&gt;"
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 9ef17c8bedf6bcef21a7c59d98a86bb20ad2da80
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752546"
---
# <a name="ltauthenticationgt-of-ltservicecertificategt-element"></a>&lt;authentication&gt; dell'elemento &lt;serviceCertificate&gt;
Specifica le impostazioni usate dal proxy del client per autenticare i certificati dei servizi ottenuti mediante la negoziazione SSL/TLS.  
  
 \<system.ServiceModel>  
\<i comportamenti >  
sezione endpointBehaviors  
\<comportamento >  
\<clientCredentials>  
\<elemento serviceCertificate >  
\<autenticazione >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<authentication customCertificateValidatorType="String" certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"   
trustedStoreLocation="LocalMachine/CurrentUser" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|customCertificateValidatorType|Stringa. Un tipo e un assembly usati per convalidare un tipo personalizzato.|  
|certificateValidationMode|Specifica una delle tre modalità usate per convalidare credenziali. Se è impostato su `Custom`, è necessario fornire anche un customCertificateValidator. Il valore predefinito è `ChainTrust`.|  
|revocationMode|Una delle modalità usate per verificare un elenco dei certificati revocati. Il valore predefinito è `Online`.|  
|trustedStoreLocation|Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`. Questo valore viene usato quando viene negoziato un certificato del servizio con il client. La convalida viene eseguita su di **persone attendibili** archiviare nel percorso dell'archivio specificato. Il valore predefinito è `CurrentUser`.|  
  
## <a name="customcertificatevalidator-attribute"></a>Attributo customCertificateValidator  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|String|Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.|  
  
## <a name="certificatevalidationmode-attribute"></a>Attributo certificateValidationMode  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|Enumerazione|Uno dei valori seguenti: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.<br /><br /> Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## <a name="revocationmode-attribute"></a>Attributo revocationMode  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|Enumerazione|Uno dei valori seguenti: NoCheck, Online, Offline.<br /><br /> Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>Attributo trustedStoreLocation  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|Enumerazione|Uno dei valori seguenti: LocalMachine o CurrentUser. L'impostazione predefinita è CurrentUser. Se l'applicazione client è in esecuzione con un account di sistema, il certificato è in genere in LocalMachine. Se l'applicazione client è in esecuzione con un account utente, il certificato è in genere in CurrentUser.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<elemento serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|Specifica un certificato da usare per l'autenticazione di un servizio presso il client.|  
  
## <a name="remarks"></a>Note  
 L'attributo `certificateValidationMode` di questo elemento di configurazione specifica il livello di attendibilità usato per autenticare i certificati. Per impostazione predefinita, il livello è impostato su `ChainTrust`. Tale impostazione prevede che ogni certificato appartenga a una gerarchia di certificati che termina in un'autorità di certificazione attendibile situata all'inizio della catena. Si tratta della modalità più sicura. Il livello può inoltre essere impostato su `PeerOrChainTrust`, a indicare che sia i certificati autocertificati (trust peer) sia i certificati appartenenti a una catena di trust sono ritenuti attendibili. Poiché i certificati autocertificati non devono essere acquistati da un'autorità attendibile, questo livello viene usato in fase di sviluppo e di debug dei client e dei servizi. Quando si distribuisce un client è invece opportuno usare il livello `ChainTrust`. È inoltre possibile impostare il valore su `Custom` o `None`. Per usare il valore `Custom` è necessario impostare anche l'attributo `customCertificateValidator` sull'assembly e sul tipo usati per convalidare il certificato. Per creare una convalida personalizzata, è necessario ereditare una classe dalla classe X509CertificateValidator astratta. Per ulteriori informazioni, vedere [procedura: creare un servizio che usa un Validator del certificato personalizzato](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
 L'attributo `revocationMode` specifica il modo in cui i certificati vengono contrassegnati per la revoca. L'impostazione predefinita è `online` a indicare che i certificati vengono contrassegnati automaticamente per la revoca. Per ulteriori informazioni, vedere [utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio vengono svolte due attività: Per prima cosa specifica un certificato del servizio che viene usato dal client per comunicare sul protocollo HTTP con endpoint il cui nome di dominio è www.contoso.com. In secondo luogo, specifica la modalità di revoca e il percorso dell'archivio usati durante l'autenticazione.  
  
```xml  
<serviceCertificate>  
  <defaultCertificate findValue="www.contoso.com"   
                      storeLocation="LocalMachine"  
                      storeName="TrustedPeople"   
                      x509FindType="FindByIssuerDistinguishedName" />  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
  <authentication revocationMode="Online"   
   trustedStoreLocation="LocalMachine" />  
</serviceCertificate>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>  
 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>  
 [Comportamenti di sicurezza](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Uso di certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Procedura: Creare un servizio che usi un validator del certificato personalizzato](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [\<authentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [Protezione di client](../../../../../docs/framework/wcf/securing-clients.md)  
 [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
